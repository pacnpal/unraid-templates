# Unraid XML Templates
A place for me to host my Unraid XML templates.

Current Templates:

<img src="https://raw.githubusercontent.com/pacnpal/simpleguardhome/refs/heads/main/static/simpleguardhome.png" width="48" align="absmiddle"> &nbsp; **[SimpleGuardHome](https://github.com/pacnpal/simpleguardhome)**

The simpleguardhome.xml file is an XML template for Unraid, designed to set up and configure SimpleGuardHome. SimpleGuardHome is a modern web application built with FastAPI and modern JavaScript, used for checking and adding domains to custom filtering rules in AdGuard Home.

Key configurations include:

    Repository: GitHub Repository
    Docker Registry: Docker Hub
    Web UI: Accessible at http://[IP]:[PORT:8000]/
    Configurations:
        Adguard Home URL: The full URL of your hosted Adguard Home instance.
        Adguard Home Port: The port used to connect to your Adguard Home instance.
        Adguard Home Username: The username for the Adguard Home user.
        Adguard Home Password: The password for the Adguard Home user.
        SimpleGuardHome WebUI Port: Port that SimpleGuardHome will be accessed at.
        Rules Backup Path: The path where SimpleGuardHome will backup rules.

For more details, visit the [project](https://github.com/pacnpal/simpleguardhome) page.

<img src="https://raw.githubusercontent.com/pacnpal/compressatorium/latest/static/images/logo.png" width="48" align="absmiddle"> &nbsp; **[Compressatorium](https://github.com/pacnpal/compressatorium)**

The compressatorium.xml file is an XML template for Unraid, designed to set up and configure Compressatorium. Compressatorium is a multi-tool game disc image converter with a web UI, supporting CHDMAN (CD/DVD/LaserDisc to CHD), Dolphin-tool (GameCube/Wii ISO/GCZ/WIA/RVZ/WBFS), and z3ds_compressor (3DS ROM compression). Features batch conversion with progress tracking, nested directory scanning, compressed archive support (ZIP, 7z, RAR), smart duplicate handling, verification, and a REST API.

Key configurations include:

    Repository: GitHub Repository
    Docker Registry: Docker Hub
    Web UI: Accessible at http://[IP]:[PORT:8080]/
    Configurations:
        WebUI Port: Port for the web interface (default 8090).
        Appdata: Persistent application data (verified files DB, metadata cache).
        Games: Primary game library. Mount additional volumes under /data/ for separate libraries.
        More Games: Optional additional game library.
        Log Level: Logs to be shown in the docker logs.
        Maximum Concurrent Jobs: Number of parallel conversion jobs.

For more details, visit the [project](https://github.com/pacnpal/compressatorium) page.

<img src="https://raw.githubusercontent.com/pacnpal/mcpelevator/main/assets/mcpelevator.png" width="48" align="absmiddle"> &nbsp; **[mcpelevator](https://github.com/pacnpal/mcpelevator)**

The mcpelevator.xml file is an XML template for Unraid, designed to set up and configure mcpelevator. mcpelevator elevates MCP servers into authenticated HTTP endpoints, self-hosted in one container: it runs stdio MCP servers (`npx`/`uvx` commands) for you and exposes each one as a remote Streamable HTTP endpoint that Claude mobile (or any MCP client) on your network can connect to. Includes a web UI with process supervision, live logs, a registry browser for one-click installs, bearer-token auth, and a Host/Origin guard.

Key configurations include:

    Repository: GitHub Repository
    Docker Registry: GitHub Container Registry (ghcr.io)
    Network: Host (so the LAN-access gate sees real client IPs)
    Web UI: Accessible at http://[IP]:[PORT:8080]/
    First login: the admin token is printed ONCE to the container log on first start.
    Configurations:
        WebUI Port: Port the control plane binds on the host (default 8080).
        Appdata: Persistent data (SQLite database, npm/uv package caches).
        Allow LAN Access: First-boot seed so the headless box is reachable from your LAN; turns control-plane auth on.
        Admin Token (break-glass): Optional token always accepted on /api, for recovery/automation.
        Public Base URL: Optional absolute URL when behind a tunnel/reverse proxy.
        Extra Allowed Hosts: Optional extra hostnames for the Host/Origin guard.
        Mint Admin Token On Boot / Max Running Servers / Start Timeout: Advanced knobs.

For more details, visit the [project](https://github.com/pacnpal/mcpelevator) page and the [Unraid deployment guide](https://github.com/pacnpal/mcpelevator/blob/main/docs/unraid.md).

<img src="https://raw.githubusercontent.com/pacnpal/wireguard-watchdog/main/assets/logo-128.png" width="48" align="absmiddle"> &nbsp; **[WireGuard Watchdog](https://github.com/pacnpal/wireguard-watchdog)**

The wg-watchdog.xml file is a Community Applications template for WireGuard Watchdog, an Unraid **plugin** that keeps a WireGuard tunnel healthy. It pings a peer through the tunnel on a schedule and bounces the tunnel via `wg-quick down/up` the moment the peer goes silent. Coexists cleanly with Unraid's built-in WireGuard support -- the watchdog never touches the interface directly, only invokes `wg-quick`.

Key configurations include:

    Plugin URL: https://raw.githubusercontent.com/pacnpal/wireguard-watchdog/main/plugin/wg-watchdog.plg
    Launch: Tools -> User Utilities -> WireGuard Watchdog
    Minimum Unraid version: 6.12.0
    Configurations:
        Enabled: Master toggle. Default `no` -- nothing runs until you enable.
        Tunnel interface: Configured WireGuard interface (e.g. `wg0`).
        Peer IP to ping: A peer reachable through the tunnel.
        Check interval: Seconds between checks (minimum 20).
        Verbose logging: If `yes`, each successful ping is logged too.
        Log file: `/var/log/wg-watchdog.log` (read-only display in the UI).

For more details, visit the [project](https://github.com/pacnpal/wireguard-watchdog) page.
