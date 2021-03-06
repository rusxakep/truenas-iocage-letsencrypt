# Q & A - truenas-iocage-letsencrypt
1. *Can I update or auto-update acme.sh within the jail using the instruction [How to upgrade acme.sh](https://github.com/acmesh-official/acme.sh#14-how-to-upgrade-acmesh)?*

   No. Doing so will overwrite any modifications made to deploy hooks when the installation script was run. More infomation in this Let's Encrypt Community Forum post [Can acme.sh deploy certs to more than one FRITZ!Box router?](https://community.letsencrypt.org/t/can-acme-sh-deploy-certs-to-more-than-one-fritz-box-router/137854/7?u=basilhendroff). To update the Let's Encrypt jail components:

   1. Save `le-config` from the original installation.

   2. Delete the jail `iocage destroy letsencrypt`. You data will remain intact as it resides outside the jail.

   3. Now repeat the installation at https://github.com/basilhendroff/truenas-iocage-letsencrypt using the saved `le-config`. Make sure you download the script again so you also have the latest script updates.

2. *How can I encrypt a second internet-facing FRITZ!Box?*

   Set up an acme.sh server in a second jail. The rule is one FRITZ!Box per acme.sh server. More infomation in this Let's Encrypt Community Forum thread [Can acme.sh deploy certs to more than one FRITZ!Box router?](https://community.letsencrypt.org/t/can-acme-sh-deploy-certs-to-more-than-one-fritz-box-router/137854).
