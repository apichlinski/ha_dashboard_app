# Home Assistant Dashboard for LG webOS TV

**A homebrew app to display your Home Assistant Lovelace dashboards directly on your LG webOS TV**

Turn your LG TV into a stunning wall-mounted smart home control panel with this simple, fullscreen homebrew application.

## Features

- **Fullscreen embedding** of any Home Assistant Lovelace dashboard via iframe
- **Support for multiple dashboards** (up to 10) – switch seamlessly using ← / → arrows on your LG Magic Remote
- **Simple on-TV configuration** – set your base URL once and add named dashboard paths
- Settings saved persistently using local storage (survives TV reboots)
- Press the **BACK** button on the remote to re-enter configuration mode at any time
- No rooting required – easy sideloading via Developer Mode
- Fully compatible with local Home Assistant instances or secure public URLs
- Optimized for remote control navigation (pair with large buttons or kiosk mode in Lovelace)

> **Pro Tip**: Install the [kiosk-mode](https://github.com/NemesisRE/kiosk-mode) HACS custom card in your Lovelace views to hide headers and sidebars for a true fullscreen experience.

## Installation

### Prerequisites
- LG TV running webOS (tested on recent models)
- Enable **Developer Mode**:
  1. Search for and install the "Developer Mode" app from the LG Content Store.
  2. Open it, sign in with a free LG Developer account, and keep it running.

### Easiest Method: webOS Dev Manager (GUI – No Command Line Needed)
1. Download the latest release from: https://github.com/webosbrew/dev-manager-desktop/releases
2. Launch the app on your computer.
3. Connect to your TV (enter TV IP address and the passphrase shown in Developer Mode app).
4. In the **Apps** tab:
   - Click **Package** and select the app folder (or the root of this repo).
   - Then click **Install** to sideload directly to your TV.

### Alternative: Download Pre-built Release
Check the [Releases page](https://github.com/apichlinski/ha_dashboard_app/releases) for the latest `.ipk` file. Install using Dev Manager or CLI.

## Usage

1. Launch the app from your TV's app list.
2. First run: Enter your Home Assistant **base URL** (e.g., `http://192.168.1.100:8123` or `https://yourdomain.duckdns.org`).
3. Add your dashboards:
   - **Name**: Friendly label (e.g., "Main", "Climate", "Security")
   - **Path**: The view path (e.g., `/lovelace/0`, `/lovelace-main/0`, or `/dashboard-tv?kiosk`)
4. Tap **Save** – the first dashboard loads in fullscreen.
5. Switch dashboards: Use **left/right arrow keys** on the Magic Remote.
6. Reconfigure anytime: Press the **BACK** button.

## Development & Building

This project includes GitHub Actions for automatic versioning and `.ipk` building.

### Local Build
```bash
npm install
npx ares-package .