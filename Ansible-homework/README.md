This Ansible is made for homework.

The file structure is the next:
.
├── ansible.cfg		# main config
├── inventory		# contain hosts
├── README.md		# Read it before use!
└── roles		# homework tasks contain here
    ├── change-password
    │   └── playbook_change-password.yml	# run if you want to change all users password except root.
    ├── NFS-share
    │   └── playbook_NFS-share.yml		# run if you want to share the NFS system from this workstation.
    ├── NFS-to-fstab
    │   └── playbook_NFS-to-fstab.yml		# run if you want the mounted NFS system mount to fstab.
    └── user-login
        └── playbook_user-login.yml		# run before all other playbook because it is the user login playbook.

USING INSTRUCTIONS:
This is how workstation can run the ansible playbooks on all hosts:
1. Open a terminal
2. Go to the folder where you downloaded my "Ansible-homework" folder
    for example: cd /tmp/Ansible2023/Ansible-homework
3. Use the next commands for purposes:
For login via ansible:
    "ansible-navigator run ./roles/user-login/playbook_user-login.yml -i inventory"

For change users password if you want (except root):
    "ansible-navigator run ./roles/change-password/playbook_change-password.yml -i inventory"

For share your NFS system if you want:
    "ansible-navigator run ./roles/NFS-share/playbook_NFS-share.yml -i inventory"

For mount the NFS system to fstab if you want:
    "ansible-navigator run ./roles/NFS-to-fstab/playbook_NFS-to-fstab.yml -i inventory"
