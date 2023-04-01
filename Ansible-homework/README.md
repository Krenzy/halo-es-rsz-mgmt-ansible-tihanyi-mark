This Ansible is made for homework.

The file structure is the next:
.
├── ansible.cfg		# main config
├── inventory		# contain hosts
├── README.md		# Read it before use!
└── roles		# contain rule, folders, playbooks and handler
    └── login-nfs-pw
        ├── 1.user-login			# run it first of all because this playbook validate and log in you as a user.
        │   └── playbook_user-login.yml
        ├── a-NFS-share				# run if you want to share NFS system from this workstation.
        │   └── playbook_NFS-share.yml
        ├── b-NFS-to-fstab			# run if you want to mounted NFS system mount to fstab.
        │   └── playbook_NFS-to-fstab.yml
        ├── c-change-password			# run if you want to change all users password except root.
        │   └── playbook_change-password.yml
        └── handler				# run this after playbook_NFS-to-fstab.yml becuase it will reboot system after fstab log present.
            └── handler.yml
