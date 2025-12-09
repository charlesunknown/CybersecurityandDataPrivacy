Pages list:
	http://localhost:8003/
	http://localhost:8003/register
	http://localhost:8003/login
	http://localhost:8003/reservation
	http://localhost:8003/reservation?id=
 	http://localhost:8003/resources
  	http://localhost:8003/resources?id=
	http://localhost:8003/api/users
	http://localhost:8003/api/resources
	http://localhost:8003/api/session

🧑‍🦲 Guest

✅ Can do

List every action a Guest can perform, with the page or endpoint. Example format:

    Can see reservations and the author is not shown
	Can add resources by accessing the url (/resources)
    Can access api/users
    Can access api/resources
    Can access api/reservation
    Can register if older than 15 years old
    Can login


❌ Cannot do

List every action that a Guest is blocked from doing. Example format:

	Can’t access the page for reservation (authorization correct)
    Cannot access api/session
    

🧑‍💼 Reserver

✅ Can do

List actions a Reserver can do according to specs + actual test results. Include visible pages and API endpoints.

Example format:

    Can add resources
	Can add reservation
    can modify resources
    can acces api/users
    can access api/resources
    Can access api/reservation
    Can access api/session
    Can escalate privileges by accessing api/

❌ Cannot do

List actions a Reserver is correctly blocked from.

Example format:

    Cannot modify their own info (GDPR violation)
    Cannot see their own info (GDPR violation)
    Cannot delete other users
    Cannot modify resources
    

🧑‍💼🛡️ Administrator

✅ Can do

List actions an Administrator can perform.

Example format:

    Can add a resource
    Can view all users (spec 4)
    Can acces api/users
    Can access api/resources
    Can access api/reservation
    Can access api/session

❌ Cannot do

List prohibited behaviors, if any, or incorrect implementation issues.

Example format:

    Can’t delete resource without accessing by a reservation with it (which then fails)
	Can’t delete Reserver (no access to list of users)
    Cannot remove reservation
    Cannot remove resource

