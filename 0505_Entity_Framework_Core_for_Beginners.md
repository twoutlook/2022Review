# Working with an Existing Database [2 of 5] | Entity Framework Core for Beginners
```
NOT WORKING 
Scaffold-DbContext "Server=MES-TEST\\sqlexpress;Initial Catalog=ContosoPizza;Persist Security Info=False;User ID=sa;Password=Easy@2022;MultipleActiveResultSets=True;Encrypt=false;TrustServerCertificate=true;Connection Timeout=30" Microsoft.EntityFrameworkCore.SqlServer -ContextDir Data -OutputDir Models
 
OK, Server only one \, not \\
 Scaffold-DbContext "Server=MES-TEST\sqlexpress;Initial Catalog=ContosoPizza;Persist Security Info=False;User ID=sa;Password=Easy@2022;MultipleActiveResultSets=True;Encrypt=false;TrustServerCertificate=true;Connection Timeout=30" Microsoft.EntityFrameworkCore.SqlServer -ContextDir Data -OutputDir Models
 

To -DataAnnotation -f (-f force to overwrite)
 Scaffold-DbContext "Server=MES-TEST\sqlexpress;Initial Catalog=ContosoPizza;Persist Security Info=False;User ID=sa;Password=Easy@2022;MultipleActiveResultSets=True;Encrypt=false;TrustServerCertificate=true;Connection Timeout=30" Microsoft.EntityFrameworkCore.SqlServer -ContextDir Data -OutputDir Models -DataAnnotation -f

Partial
 Scaffold-DbContext "Server=MES-TEST\sqlexpress;Initial Catalog=ContosoPizza;Persist Security Info=False;User ID=sa;Password=Easy@2022;MultipleActiveResultSets=True;Encrypt=false;TrustServerCertificate=true;Connection Timeout=30" Microsoft.EntityFrameworkCore.SqlServer -ContextDir Data -OutputDir Models/Generated -ContextNamespace ContosoPizza.Data -Namespace ContosoPizza.Models


dotnet ef dbcontext 
to see Commands:
dotnet ef dbcontext scaffold --help

```