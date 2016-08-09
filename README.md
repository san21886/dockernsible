1. Install ansible using ansible/install_ansible
2. Configure ansible inventory file: ansible/playbooks/inventory
3. Install docker engine on all nodes using playbook: ansible/playbooks/install_docker_engine.yml
    ansible-playbook install_docker_engine.yml -i inventory
4. Docker engine operations:
    ansible-playbook start_docker.yml -i inventory
    ansible-playbook stop_docker.yml -i inventory
    ansible-playbook configure_docker.yml -i inventory
5. Etcd operations:
    ansible-playbook start_etcd.yml -i inventory
    ansible-playbook stop_etcd.yml -i inventory
6. Configure Swarm:
    ansible-playbook swarm_cluster_setup_tasks.yml -i inventory
7. Setup docker private registry.
    configure inventory in file inventory.
    confugre registry config docker_registry_config.yml
    ansible-playbook setup_docker_registry.yml -i inventory
8. Stop all running non swarm containers
    ansible-playbook docker_stop_running_containers.yml -i inventory
9. Start all exited non swarm containers
    ansible-playbook docker_start_stopped_containers.yml -i inventory
10. Remove all exited non swarm containers
    ansible-playbook docker_remove_stopped_containers.yml -i inventory
