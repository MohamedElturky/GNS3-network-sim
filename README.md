# Networks Lab — GNS3 Project

**Project Overview**
- **Purpose:** A GNS3-based networks lab project for learning device configuration, interconnections, and basic troubleshooting.
- **Tools:** GNS3 (project file), Dynamips (IOS emulation), VPCS (virtual PCs).

**Topology**
- **Description:** A small multi-device lab composed of four IOS routers (Dynamips) and several VPCS endpoints. The topology demonstrates basic routing, interface configuration, and connectivity testing between segments.

**Files & Structure**
- **GNS3 Project:** [Networks Lab/Networks Lab.gns3](Networks%20Lab/Networks%20Lab.gns3)
- **Dynamips devices and configs:** project-files/dynamips contains per-device folders with logs and startup configs. Example paths:
	- [project-files/dynamips/58b7531c-c42d-477a-8fc4-3391e9c8f3c6/configs/i1_startup-config.cfg](project-files/dynamips/58b7531c-c42d-477a-8fc4-3391e9c8f3c6/configs/i1_startup-config.cfg)
	- [project-files/dynamips/9fe91a4a-774d-43d6-9c4b-36285a8642da/configs/i2_startup-config.cfg](project-files/dynamips/9fe91a4a-774d-43d6-9c4b-36285a8642da/configs/i2_startup-config.cfg)
	- [project-files/dynamips/77595266-ec59-4d11-b990-461de665f661/configs/i4_startup-config.cfg](project-files/dynamips/77595266-ec59-4d11-b990-461de665f661/configs/i4_startup-config.cfg)
- **VPCS startup files:** stored under project-files/vpcs; example: [project-files/vpcs/1bf7ee98-65c0-4a04-b9a1-0973e52c58f8/startup.vpc](project-files/vpcs/1bf7ee98-65c0-4a04-b9a1-0973e52c58f8/startup.vpc)

**How to Open the Lab**
- **Open project:** Launch GNS3 and open the project file at [Networks Lab/Networks Lab.gns3](Networks%20Lab/Networks%20Lab.gns3).
- **Start devices:** Use the GNS3 GUI to start routers and VPCS. Start Dynamips nodes first where applicable, then VPCS endpoints.

**Running the Lab — Quick Steps**
- **1. Verify prerequisites:** GNS3 installed and configured with Dynamips and VPCS support.
- **2. Load project:** Open the GNS3 project file listed above.
- **3. Start topology:** Start all devices using the GNS3 play/start button.
- **4. Restore configs (if needed):** For a router console, paste the contents of the corresponding `i?_startup-config.cfg` into the router in config mode or replace the node's startup-config file in the device folder and restart the node.
- **5. Test connectivity:** From VPCS consoles use `ping` to check connectivity between segments. From routers use `show ip route`, `show ip interface brief`, and interface `ping` tests.

**Configuration Notes**
- **Startup configs:** Each Dynamips device folder contains a `configs` subfolder with startup-config files; these are safe to reuse or adapt.
- **Logs:** Dynamips logs and stdout files are present in the device folders and can help troubleshoot boot and interface issues.

**Troubleshooting**
- **Node fails to start:** Check the Dynamips log files in the device folder for errors. Ensure the correct IOS image and sufficient RAM are configured in GNS3 preferences.
- **No connectivity:** Confirm interfaces are up on both ends (`no shutdown`), correct IP addressing, and that route/OSPF/static routes are configured as expected.

**Notes & Maintenance**
- Keep backups of the `configs` folder for each device if you plan to modify startup configs.
- VPCS startup scripts can be edited to set IPs and routes automatically when VPCS starts.
