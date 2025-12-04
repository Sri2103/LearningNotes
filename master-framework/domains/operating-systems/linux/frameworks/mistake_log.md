# Linux Mistake Log

## Common Mistakes I've Made

- Deleting files without checking inode usage
- Restarting services without checking logs
- Misusing chmod recursively
- Confusing user/group permissions
- Forgetting systemctl enable

## Fix Strategy

- Always inspect with ls -l first
- Always check journalctl
- Create a dry-run plan before commands
