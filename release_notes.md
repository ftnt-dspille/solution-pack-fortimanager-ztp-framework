# What's New

Release of 1.0.8
- Add 7.6.2 compatibility with playbook origin and editable flag support
- Add new playbook to unlock all playbooks in the ZTP solution pack
- Enhance Jinja templates for monitoring task execution time and policy script execution
- Add logic to handle Jinja template rendering errors with device comments
- Improve ZTP profile lookup performance using 7.6.2 loop breaking feature
- Enhance missing metadata prompts with direct device record linking
- Fix processing issue with running linked scripts on devices
- Add task parameters for device authorization
- Improve device name changing to use global device level
- Add 7.6.2 dashboard defaults and MMD changes
- Enhance format return for easier device IRI linking in dialogs
- Enhance comment creation for script results

Release of 1.0.4:
 - Fix problems with running in FSR 7.5.x. 
 - Add support for FMG Workspace mode. 
 - Add a task monitor playbook for tasks that take a long time. 
 - Modify the ZTP Profile Record View to ease editing settings. 
 - Fix multiple issues outlined in the repo>issues.
 - Update random device model creation to use supported device models as listed by the FMG `/pm/config/adom/<adom>/_data/dvm/device/model` resource. 

Release of 1.0.3:
 - Add support for an exciting new Script Type: `Custom`
 - Modify ZTP Profile auto-assign to be more efficient and stop rendering device searches once the profile is found. 

Release of 1.0.2:
 - Add jinja vars support to ztp profile assignments and update docs to reflect this change.

# Known Bugs

## Dashboard Dynamic Content ( 0932566 )

If you are updating an existing solution pack then the included Announcement might be auto-incremented. This impacts the Dashboard Quick Links. To fix this SSH into FortiSOAR and run the following command until this is fixed. 

```
sudo su -
env PGPASSWORD=$(cat /home/csadmin/device_uuid) psql -U cyberpgsql -d venom -c "update announcements set id=1 where uuid='83ca88a8-e02f-48a1-901f-39aede335b7d';"
```
See internal Bug ID `0932566` for the latest status of the bug.
