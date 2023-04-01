This Ansible is made for homework.

The file structure is the next:
.
├── ansible.cfg		# main config
├── inventory		# contain hosts
├── README.md		# Read it before use!
└── roles		    # contain rule, folders, playbooks and handler
    └── login-nfs-pw
        ├── 1.user-login			# run this playbook first of all because this playbook validate and log in you as a user.
        │   └── playbook_user-login.yml
        ├── a-NFS-share				# run this playbook if you want to share NFS system from this workstation.
        │   └── playbook_NFS-share.yml
        ├── b-NFS-to-fstab			# run this playbook if you want to mounted NFS share to fstab.
        │   └── playbook_NFS-to-fstab.yml
        ├── c-change-password		# run this playbook if you want to change all users password except root.
        │   └── playbook_change-password.yml
        └── handler				    # run this playbook after playbook_NFS-to-fstab.yml becuase it will reboot system after fstab log present.
            └── handler.yml

USING INSTRUCTIONS: This is how workstation can run the ansible playbooks on all hosts:

1.	Open a terminal
2.	Go to the folder where you downloaded my "Ansible-homework" folder for example: cd /tmp/Ansible2023/Ansible-homework
3.	Use the next commands for purposes: For login via ansible: "ansible-navigator run ./roles/login-nfs-pw/1.user-login/playbook_user-login.yml -i inventory"

For change users password if you want (except root): "ansible-navigator run ./roles/login-nfs-pw/c-change-password/playbook_change-password.yml -i inventory"

For share your NFS system if you want: "ansible-navigator run ./roles/login-nfs-pw/a-NFS-share/playbook_NFS-share.yml -i inventory"

For mount the NFS system to fstab if you want: "ansible-navigator run ./roles/login-nfs-pw/b-NFS-to-fstab/playbook_NFS-to-fstab.yml -i inventory"
