# Nearby users&chats
How to work with geolocation-based features like geochats and the nearby users feature.
### Fetching nearby users and geogroups
Use contacts.getLocated to fetch a list of nearby users and groups.
Do not set any of the background, self_expires flags: only populate geo_point with the current geolocation of the user: a list of users and geochats located nearby will be returned (without publishing the current location of the user).
This functionality is useful for example to exchange contacts with a nearby Telegram user, or join a location-based group chat, see here » for more usecases.
See here » for more info on how to create a geogroup, and here » for more info on how to advertise our current location to other users.
### Creating a geogroup
Pass a geo_point to channels.createChannel when creating a supergroup in order to create a geogroup associated to a geolocation, that will be returned to nearby users ».
A textual description of the location (1-64 UTF-8 chars) should also be passed in address.
Use channels.editLocation to change the group's location.
### Advertising our current location
Our current location may be advertised to other users using contacts.getLocated: in this case the self_expires flag must always be set.
This flag is used to specify the expiration TTL of the passed geolocation (i.e. the geolocation will expire after self_expires seconds); pass 0x7fffffff to disable expiry, 0 to make the current geolocation private.
The method will also return a list of nearby users and chats, but only if the passed expiration TTL is not equal to zero.
Users may still fetch nearby users and chats without making their geolocation public by simply not setting the flag, see here » for more info.
While the geolocation of the current user is public, clients should update it in the background every half-an-hour or so (or in any case before the expiration date specified with self_expires), while setting this flag: if the new location is more than 1 KM away from the previous one, or if the previous location is unknown, the background flag should be set.
