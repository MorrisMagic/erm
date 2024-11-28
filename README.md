Gymnasium

Attributes:
Gymnasium_ID (Primary Key)
Name
Address
Phone_Number
Member

Attributes:
Member_ID (Primary Key)
Last_Name
First_Name
Address
Date_of_Birth
Gender
Gymnasium_ID (Foreign Key to Gymnasium)
Session

Attributes:
Session_ID (Primary Key)
Sport_Type
Schedule
Max_Members (fixed to 20)
Gymnasium_ID (Foreign Key to Gymnasium)
Coach

Attributes:
Coach_ID (Primary Key)
Last_Name
First_Name
Age
Specialty
Registration (Associative Entity to track Member registrations in Sessions)

Attributes:
Registration_ID (Primary Key)
Member_ID (Foreign Key to Member)
Session_ID (Foreign Key to Session)
Date_Registered (date the registration was made)
Session_Coach (Associative Entity to track which Coaches lead which Sessions)

Attributes:
Session_ID (Foreign Key to Session)
Coach_ID (Foreign Key to Coach)
Relationships
Gymnasium – Member (One-to-Many)

A gymnasium can have many members.
A member is registered at one gymnasium.
Gymnasium – Session (One-to-Many)

A gymnasium can have many sessions.
A session is held at one gymnasium.
Session – Member (Many-to-Many)

A session can accommodate many members (up to 20).
A member can register for many sessions.
This relationship is represented by the Registration associative entity.
Session – Coach (Many-to-Many)

A session can have up to 2 coaches.
A coach can lead many sessions.
This relationship is represented by the Session_Coach associative entity.
ER Diagram Representation
Here is the ER diagram description:

Gymnasium (1) — (M) Member
Gymnasium (1) — (M) Session
Session (M) — (M) Member (through Registration)
Session (M) — (M) Coach (through Session_Coach)
ER Diagram Textual Breakdown
Entities:
Gymnasium:

Attributes: Gymnasium_ID (PK), Name, Address, Phone_Number.
Member:

Attributes: Member_ID (PK), Last_Name, First_Name, Address, Date_of_Birth, Gender, Gymnasium_ID (FK).
Session:

Attributes: Session_ID (PK), Sport_Type, Schedule, Max_Members, Gymnasium_ID (FK).
Coach:

Attributes: Coach_ID (PK), Last_Name, First_Name, Age, Specialty.
Registration (Associative Entity for Member-Sessions):

Attributes: Registration_ID (PK), Member_ID (FK), Session_ID (FK), Date_Registered.
Session_Coach (Associative Entity for Session-Coach relationship):

Attributes: Session_ID (FK), Coach_ID (FK).
Relationships:
Gymnasium - Member:

A Gymnasium can have many Members.
A Member belongs to exactly one Gymnasium.
Cardinality: 1-to-Many (Gymnasium to Members).
Gymnasium - Session:

A Gymnasium can have many Sessions.
A Session is conducted in exactly one Gymnasium.
Cardinality: 1-to-Many (Gymnasium to Sessions).
Session - Member:

A Session can accommodate many Members (up to 20).
A Member can register for many Sessions.
Cardinality: Many-to-Many (Sessions to Members) — represented by the Registration associative entity.
Session - Coach:

A Session can be led by up to 2 Coaches.
A Coach can lead many Sessions.
Cardinality: Many-to-Many (Sessions to Coaches) — represented by the Session_Coach associative entity.
Assumptions and Notes
Max Members per Session:
The number of members allowed in a session is capped at 20, which is noted in the Session entity.

One-to-Many Relationship between Gymnasium and Sessions/Members:
Each session and member is linked to exactly one gymnasium, but a gymnasium can have multiple sessions and members.

Many-to-Many Relationship between Sessions and Members:
A member can attend multiple sessions, and each session can have multiple members. This is tracked in the Registration entity, where each registration represents a member attending a specific session.

Session-Coches Relationship:
Each session can have multiple coaches (up to two), and each coach can be involved in multiple sessions. This relationship is managed via the Session_Coach associative entity.
