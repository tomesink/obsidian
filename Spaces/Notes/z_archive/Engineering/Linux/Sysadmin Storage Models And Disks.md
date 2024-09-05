---
up: 
tags: []
---
1. Direct Attached Storage (DAS): This is a digital storage system directly
   attached to a server or PC via cable, and there is no network involved. DAS
   devices could include hard drives or SSDs. The key advantages are its
   simplicity and relatively low cost. However, the storage isn't easily
   expandable or highly available, because data can't be accessed if the server
   or PC it's attached to has a problem.
2. Network Attached Storage (NAS): This is a type of dedicated file storage
   device which provides data access to clients that are connected over a
   network. The key advantage of NAS is its ability to provide multiple users
   on the network with access to the same files. However, because NAS relies on
   Ethernet connectivity, it may not offer the level of performance that some
   applications need.
3. Storage Area Network (SAN): This is a network designed to allow multiple
   servers to access shared storage devices across a special-purpose network.
   SANs are often used in environments that require high-speed data transfer,
   such as data centers. Unlike NAS, which uses Ethernet, SAN can use block-
   based storage over fibre channel, providing superior performance.
4. Cloud Storage: This is a service where data is stored, maintained, and
   backed up remotely and made available to users over a network (typically the
   Internet). Cloud storage is scalable, meaning users can increase or decrease
   the amount of storage they're paying for based on their current needs. It
   also provides a geographically dispersed architecture, meaning if a disaster
   occurs at one location, data can be accessed from another location. However,
   cloud storage typically has a recurring cost and requires a stable internet
   connection for data access.

Cloud storage models:
**file level**: Client access to file level. Dropbox, GDrive, iCloud

**object level** : Client acces to object level. AWS S3(amazon simple storage), hides filesystem implementation details from
the client and provides easy abstraction for the API.

**block level**: client access to block level. allows to create filesystems and partitions to fit the
needs. AWS EBS (Elastic Block Store)