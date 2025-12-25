### Update to the latest version with a script

You can execute `user-update-to-latest-version.sh` as `user` to update the app to the latest version.

The script will also create a backup git branch called `previous-version` with your current version.

Example:

```
bash ~/scripts/updates/user-update-to-latest-version.sh
```

### Revert to a previous version with a script

You can execute `user-revert-to-previous-version.sh` as `user` to revert the app to the previous version if the `previous-version` git branch exists (e.g., if a backup was created by the `user-update-to-latest-version.sh` script).

Example:

```
bash ~/scripts/updates/user-revert-to-previous-version.sh
```

### Troubleshooting

##### Unable to create index.lock git file

If you get the following errors:

```
fatal: Unable to create '~/apps/spasm-forum/frontend/.git/index.lock': File exists.
fatal: Unable to create '~/apps/spasm-forum/backend/.git/index.lock': File exists.
```

Then try deleting the lock files manually:

```
rm ~/apps/spasm-forum/frontend/.git/index.lock
rm ~/apps/spasm-forum/backend/.git/index.lock
```

And then execute the update script again:

```
bash ~/scripts/updates/user-update-to-latest-version.sh
```


