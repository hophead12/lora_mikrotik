# Ansible Playbook for LoRa Device Settings on Mikrotik

This Ansible playbook is designed to automate the configuration of LoRa devices on Mikrotik routers. It allows you to manage multiple Mikrotik devices from a central location.

## Prerequisites

- Ansible installed on the control machine
- SSH access to the Mikrotik routers

## Usage

1. Add the IP addresses or hostnames of your Mikrotik routers to the `inventory` file.

2. Update the `group_vars/all.yml` file with the appropriate credentials (username and password) and LoRa device settings. You can use the `ansible-vault` command to encrypt sensitive data:

> ansible-vault edit group_vars/all.yml

Here, you can change parameters like LoRa device name, DevEUI, AppEUI, AppKey, uplink/downlink ports, etc.

3. Run the playbook using the following command:

> ansible-playbook lora_mikrotik.yaml -i inventory


his command will execute the `lora_mikrotik.yaml` playbook on all hosts listed in the `inventory` file.

## Playbook Structure

The `lora_mikrotik.yaml` playbook includes the following tasks:

- Enable LoRaWAN on the Mikrotik router
- Configure the LoRaWAN server settings
- Add LoRaWAN network servers
- Add or modify LoRaWAN device configurations

You can review and modify the tasks in the playbook according to your specific requirements.

## Customization

To customize the playbook for your environment, you can modify the following files:

- `ansible.cfg`: You can add more forks or own parameters.
- `inventory`: Update this file with the IP addresses or hostnames of your Mikrotik routers.
- `group_vars/all.yml`: Modify the variables in this file to match your desired LoRa device settings and Mikrotik credentials.
- `lora_mikrotik.yaml`: Adjust the tasks in this playbook file if you need to add, modify, or remove specific configurations.

## License

This project is licensed under the [MIT License](LICENSE).
