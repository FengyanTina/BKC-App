# Navigate to your main solution directory
cd path\to\BKC-Web-Api

# Create the Web.Api project
dotnet new webapi -o Web.Api

# Create the Core project (Class Library)
dotnet new classlib -o Core

# Create the Infrastructure project (Class Library)
dotnet new classlib -o Infrastructure

# Create the Application project (Class Library)
dotnet new classlib -o Application


dotnet new sln -n BKC to create BKC.sln


dotnet sln BKC.sln  add Api/Api.csproj
dotnet sln BKC.sln add Application/Application.csproj
dotnet sln BKC.sln add Core/Core.csproj
dotnet sln BKC.sln add Infrastructure/Infrastructure.csproj


# For Api referencing BKC.Application and BKC.Infrastructure
cd Api
dotnet add reference ../Application/Application.csproj
dotnet add reference ../Infrastructure/Infrastructure.csproj
cd ..

# For Application referencing BKC.Core
cd Application
dotnet add reference ../Core/Core.csproj
cd ..

# For Infrastructure referencing BKC.Core
cd Infrastructure
dotnet add reference ../Core/Core.csproj
cd ..


cd Infrastructure
dotnet add package Microsoft.EntityFrameworkCore
dotnet add package Pomelo.EntityFrameworkCore.MySql

