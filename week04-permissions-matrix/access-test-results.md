Create: Allowed, created text file called hr-test-create.txt

Edit and Save: Allowed, edited and saved hr-test-create.txt

Delete Admin File: Allowed, deleted admin created file, DELETEADMINFILE

Change Security Settings: Denied, was not able to change admins privileges 


Permissions Matrix Table:

HR-Managers
NTFS: Full Control
Share: Full Control
Network Access: Full Control
Test Result: Validated

HR-Staff
NTFS: Modify (Read, Write, Execute, Delete)
Share: Change
Network Access: Change / Modify
Test Result: Tested account; it can create, edit, and delete files; cannot modify secuity settings

Audit-Readonly
NTFS: Read & Execute
Share: Read
Network Access: Read
Test Result: Validated


Access Design Choices:
To follow the principle of least privilege Audit-Readonly is restricted to Read permissions because the auditors only require to read file, not change or delete them, increasing their permissions would add unnecessary risk. This is why removing the default Everyone group eliminates access to the sensitive payroll data across the network, ensuring that only authorized groups can have access. 
