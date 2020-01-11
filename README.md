# api-asp.netcore
This is an api made by an practical guide of Microsoft Learning. The objective of this API was that learn the concepts and ways to create for an API in ASP.NET Core.


Nota para mis amigos: 

Para consumir la API necesitan al menos hacer una conexión de bases de datos.

1. En Startup.cs hay un código que es: "services.AddDbContext<ContosoPetsContext>(options => options.UseSqlServer(Configuration.GetConnectionString("DefaultConnectionString")));" en la parte de (options => options.UseSqlServer) deben cambiarlo a la base de datos que van a utilizar (cualquier cosa me preguntan en privado) sin embargo dejo una guía de como hacerlo dependiendo de la base de datos en cuestión: https://medium.com/@daniel.sagita/using-database-in-asp-net-core-f69f99048bb hay que instalar dependencias con Nuget dependiendo de la base de datos. No tarda nada y es sencillo:

Dependencies
"
- In case you’re using ASP.NET Core application, you will need to install some dependencies that is available through nuget SQL Server (Microsoft.EntityFrameworkCore.SqlServer) is included in the Microsoft.AspNetCore.App metapackage so you don’t need to install the dependencies anymore.

- MySQL. Currently there are 2 options that you can use for using EF Core in MySQL. That is Pomelo.EntityFrameworkCore.MySql (created by the community based on MySqlConnector) and MySql.Data.EntityFrameworkCore (created by the MySQL team based on MySql.Data). Either one is fine and can get you up and running.

- PostgreSQL. You will need to install Npgsql.EntityFrameworkCore.PostgreSQL which is based on Npgsql, the data access library for PostgreSQL.

"

También se puede usar SQLite, sólo hay que cambiar el options.UseSqlServer a options.UseSqlite.


Luego se define la conexión a la base de datos en appsettings.json, en DefaultConnectionString:

- "Data Source= aquí pones el servidor(localhost, etc)"
- "Initial Catalog= aquí pones el nombre de la base de datos"

En el caso de Sqlite, creo que es igual, sin embargo aquí en la documentación hay una guía super corta de hacerlo con Sqlite: https://docs.microsoft.com/en-us/aspnet/core/tutorials/razor-pages/sql?view=aspnetcore-3.1&tabs=visual-studio-code


