
### <a name="access"></a> Access Base
User roles, role groups, permissions are all defined here. For permission checks (other than biometric confirmation), every module visits Access Base.

- All the data regarding permissions, roles and similar will be retained in a conventional database (SQL based).
- An API is needed to perform role checks, permission validations, or alterations. Otherwise, directly sending sql queries to this module is both dangerous and clunky.
- Good candidate for API is Lumen. Simple and lightweight. Alternative is NodeJS.
- If some sort of proper interface is required or advanced capabilities is a must, then Laravel is a good fit. Alternative NodeJS, or some Python framework (Flask ?).
- The API is expected to be lighting fast since big chunk of actions and functions eventually hit this endpoint.
- This module is closed to remote access by all means.
#### Definitions:
**Permission:** Single instruction that testifies a permit to do an action. Examples: 'Read public file from [Storage](/storage/storage.md)', 'Edit [Exposer](#exposer) settings'

**Role:**  Slugs/tags for each user and [module](/req.md#module) in the ecosystem. For the sake of simplicity each user has one role: ```(n)user->(1)role``` . Of course there can be other users or modules with the same role. Example: 'guest','master','local master','telemetry module'. Allowing multiple roles per user is still in consideration.

**Role Permissions:** Standard permissions for a given role. Example
Master Permissions: 'Edit [overseer](#overseer)', 'Initiate FIN protocol', 'Read telemetry data' etc.
Guest permissions: 'Connect to dns server', "connect to media hub's broadcast"
```(n)role->(n)permission```

**User Permissions:** Each user/module gets its permissions from two sources. One is inheriting from given role's permissions, other is from exclusive permissions.
```
Example scenario:
- Guest permissions: "Connect to dns server", "connect to media hub's broadcast"
- User #46 is a user with "Guest" role
- User #46 is given the exclusive permission: "Access web server on port:80"
- User #46's permissions: "Connect to dns server", "connect to media hub's broadcast", "Access web server on port:80"

```
