## Schema

The Schema consists of a User table, a UserAudit table and a ResetPasswordToken table
1. User table
    - Conists of the user authentication information including
        - User first name
        - User last name
        - User email
        - The hashed user password
        - The salt that is used to hash user password
        - When the user was created
    - There can only be one user record per email
2. UserAudit table
    - Consists of audit data and authorization information including
        - The date the user logged in 
        - The IP the user logged in from
        - The JWT cookie that is generated at login
        - The expiry date of the cookie   
    - Each time a user logs in, a new record is created
3. ResetPasswordToken table
    - Conists of the data associated with a reset password token including
        - The hashed token
        - The salt that is used to hash the token
        - The expiration date of the token
    - A token is sent along with a reset password email and is deleted each time a user requests a new one  

![image](https://github.com/trobs98/login_auth_schema/assets/45018105/94027bbc-44fc-49f1-b393-3546f7a6e009)


### Setup - WSL2 - Ubuntu
To setup the database, import the user_schema.sql file into your MySQL server using the following command:

`mysql -u <USER> -p <PASSWORD> < user_schema.sql`
