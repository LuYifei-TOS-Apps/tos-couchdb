# CouchDB on TOS privacy policy

CouchDB runs on your TNAS. It stores user-supplied JSON documents, attachments, database metadata, indexes and authentication settings in the TOS application data directory mounted at `/var/lib/tos-couchdb`. The NAS administrator configures access and manages logs and backups.

Authorized users access databases through Fauxton or the HTTP API. If an administrator enables replication, CouchDB exchanges the selected database content with the configured peers. Installation and updates can contact the TOS platform, GitHub and Docker Hub to retrieve the package and image.

Authorized users can view, edit and delete documents through CouchDB. Retention of old revisions, logs and backups depends on database maintenance and administrator settings. Contact the NAS administrator for data requests. Protect access with database permissions and use TLS on untrusted networks.
