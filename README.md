# Unraid XML Templates
A place for me to host my Unraid XML templates.

Current Templates:

[SimpleGuardHome](https://github.com/pacnpal/simpleguardhome)

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
