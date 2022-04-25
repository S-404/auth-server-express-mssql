# auth-server-express-mssql

## prepare mssql db

add tables to 'AUTH' database

users: 

        USE [AUTH] 
        GO 
        SET ANSI_NULLS ON
        GO
        SET QUOTED_IDENTIFIER ON
        GO
        CREATE TABLE [dbo].[users](
          [id] [int] IDENTITY(1,1) NOT NULL,
          [username] [nvarchar](16) NOT NULL,
          [password] [nvarchar](max) NOT NULL,
          [email] [nvarchar](max) NOT NULL,
          [isActivated] [bit] NULL
        ) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
        GO
tokens: 

        USE [AUTH]
        GO
        SET ANSI_NULLS ON
        GO
        SET QUOTED_IDENTIFIER ON
        GO
        CREATE TABLE [dbo].[tokens](
          [id] [int] IDENTITY(1,1) NOT NULL,
          [userId] [int] NOT NULL,
          [refreshToken] [nvarchar](max) NULL,
          [createdAt] [datetime] NULL,
          [updatedAt] [datetime] NULL
        ) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]
        GO
        
## prepare .env file

        PORT=5005
        CLIENT_URL=http://localhost:3000

        JWT_ACCESS_SECRET=access_secret_key
        JWT_REFRESH_SECRET=refresh_secret_key
        HASH_SALT=3

        DB_USER=user
        DB_USER_PASSWORD=password
        DB_SERVER_NAME=DESKTOP-N22222U

        DB_AUTH_DATABASE_NAME=AUTH
        
## use script

      npm start
  
