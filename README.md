# WG-VPN
WG VPN is a lightweight WireGuard-compatible VPN client optimized for Fire TV. Import .conf or .zip profiles, connect/disconnect, monitor live traffic, and choose to exit while keeping the VPN connected in the background.
<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
</head>
<body>
    <h1>WG VPN Logo</h1>
    <img src="https://raw.githubusercontent.com/ilblogdicristiangallo/WG-VPN/109305d887c67d01d7da55093b13fade7dca046b/ScreenShot/logo-wireguard-app.png" alt="WG VPN Logo">
</body>
</html>
# WG VPN (Fire TV)

WG VPN is a lightweight **WireGuard-compatible** VPN client optimized for **Amazon Fire TV** and remote control navigation.

It lets you import WireGuard configuration profiles (`.conf`) (also from `.zip` archives), connect/disconnect quickly, and monitor real-time traffic (RX/TX).

## Features

- WireGuard-compatible VPN tunnel control (**Connect / Disconnect**)
- Import VPN profiles from:
  - `.conf` files
  - `.zip` archives containing one or more `.conf` (and optionally `.txt`) files
- TV-friendly UI:
  - D-pad navigation (Up/Down/Left/Right)
  - OK/Enter to select
- Connection status indicator (**CONNECTED / OFF**)
- Real-time traffic statistics:
  - Download (RX)
  - Upload (TX)
- Profile management:
  - List saved profiles
  - Remove a profile
- Exit menu (Back button):
  - **Exit (keep VPN connected)**: the app goes to background (like HOME)
  - **Disconnect & Exit**
  - Cancel

## Requirements

- A working **WireGuard-compatible VPN server**
- A valid WireGuard configuration file (`.conf`)
- Android/Fire OS VPN permission (the app prompts when connecting)

> This app does **not** provide built-in VPN servers. You must supply your own configuration.

## How it works (high level)

- The Flutter UI communicates with Android using a `MethodChannel`.
- On Android, the app uses the WireGuard Android backend (`GoBackend`) to bring a tunnel **UP** or **DOWN**.
- The app can query:
  - tunnel state (`UP` / `DOWN`)
  - traffic counters (total RX/TX)

## Usage (Fire TV)

1. Open the app.
2. Press **+** to import a profile (`.conf`) or a `.zip` containing `.conf` files.
3. Select a profile and choose **Connect**.
4. Accept the Android VPN permission prompt.
5. When connected, the status shows **CONNECTED • ON** and RX/TX counters update.

### Disconnect
- Open the profile menu and select **Disconnect**.

### Exit behavior (Back button)
When pressing **Back** on the home screen, an exit menu is shown:
- **Exit (keep VPN connected)**: sends the app to background (VPN stays connected)
- **Disconnect & Exit**: disconnects the VPN and exits
- **Cancel**: stays in the app

## Permissions

Depending on Android/Fire OS version, the app may request storage permissions to read `.conf`/`.zip` files.
Imported profiles are stored locally in the app’s documents directory.

## Privacy

- No account registration/login
- No ads
- No analytics SDKs
- Imported configuration files are stored locally on the device
- Network traffic is routed through the VPN server configured by the user profile

## Disclaimer / Trademark

WireGuard is a registered trademark of Jason A. Donenfeld.  
This app is **not affiliated with or endorsed by** the WireGuard project.

