# 📜 Network Automation Playbook Directory

This repository contains a structured collection of Ansible playbooks for Juniper fabric orchestration. The list follows the specific serial order used for development and lab operations.

| Serial # | Playbook Name | Purpose / Function |
| :--- | :--- | :--- |
| **1** | `connectivity.yml` | Establishes base connectivity (NETCONF) to Juniper. |
| **2** | `gather_mgmnt_data.yml` | Collects management-plane data and filters variables for clean inventory use. |
| **3** | `ubuntu_save.yml` | Saves the running configuration directly to the local Ubuntu management server. |
| **4** | `save_config_local_machine.yml` | Captures and backups device configurations into organized local directories. |
| **5** | `lldp_adjecency.yml` | Scrapes LLDP neighbor details to verify physical cabling against design topology. |
| **6** | `sh_bgp_summary.yml` | Provides a real-time summary of BGP peering status to ensure control-plane stability. |
| **7** | `json_bgp` | Converts BGP status into JSON format for programmatic data parsing and logic. |
| **8** | `golden_configs.yml` | Deploys standardized "Golden Configuration" templates to NY and Carolina fabric nodes. |
| **9** | `config_push.yml` | Pushes specific configuration snippets to targeted leaf switches for unit testing. |
| **10** | `customer_config.yml` | Dynamically applies site-specific customer settings to the existing fabric. |
| **11** | `health_checker_raw.yml` | Audits device health using raw `stdout` and `stdout_lines` output comparisons. |
| **12** | `health_checker_formatted.yml` | Scrapes CLI data and correlates it against thresholds for high-fidelity health reporting. |
| **13** | `health_checker_save_jinja.yml` | Uses Jinja2 templates to save structured snapshots of network state for validation. |
| **14** | `health_checker_save_locally.yml'. |dup -check notepad notes. This is less efficient version than #13. |

---

### **Quick Setup**
To run any playbook from this directory, ensure your inventory is configured and use:
```bash
ansible-playbook -i inventory.ini <playbook_name>.yml

you may have to specify .ini using -i ~/Juniper/ansible-hosts.ini in certain cases 
