# Upgrading Ghost for development
1. Change to project root.
2. `git checkout master && git pull upstream master && yarn && bower install`
3. `git checkout emerge-admin && git rebase master`
4. `cd core/client`
5. Repeat steps 3 & 4.

# Working in Ghost
1. `grunt dev` at root - Starts server and watches for changes.
2. Add a comment to all changes with `idiva` at the end.

# Push changes to server
1. Change to local project root.
2. `git push origin emerge-admin`
3. `cd core/client` and repeat step 2.
4. Copy ghost user password from Lastpass.
4. `ssh root@emerge-writerscolony.org && cd /var/www/ghost-1-5/versions/emerge-admin && su cat`
5. `git pull origin emerge-admin` in root and `core/client`.
6. `yarn run build --environment=production` in `core/client`.
6. Change to remote project root and `npm link ../gsync`.
7. `ghost start` - Test the project. If there are issues, check for error messages with `ghost run`.