# Working with an Existing Database [2 of 5] | Entity Framework Core for Beginners

## NuGet
- Microsoft.EntityFrameworkCore.Design
- Microsoft.EntityFrameworkCore.SqlServer
- Microsoft.EntityFrameworkCore.Tools

```

  <ItemGroup>
    <PackageReference Include="Microsoft.EntityFrameworkCore.Design" Version="6.0.4">
      <PrivateAssets>all</PrivateAssets>
      <IncludeAssets>runtime; build; native; contentfiles; analyzers; buildtransitive</IncludeAssets>
    </PackageReference>
    <PackageReference Include="Microsoft.EntityFrameworkCore.SqlServer" Version="6.0.4" />
    <PackageReference Include="Microsoft.EntityFrameworkCore.Tools" Version="6.0.4">
      <PrivateAssets>all</PrivateAssets>
      <IncludeAssets>runtime; build; native; contentfiles; analyzers; buildtransitive</IncludeAssets>
    </PackageReference>
  </ItemGroup>
 ``` 

## working with DataAnnotation and Partial, with specific Namespace as well
-  Scaffold-DbContext "Server=MES-TEST\sqlexpress;Initial Catalog=ContosoPizza;Persist Security Info=False;User ID=sa;Password=Easy@2022;MultipleActiveResultSets=True;Encrypt=false;TrustServerCertificate=true;Connection Timeout=30" Microsoft.EntityFrameworkCore.SqlServer -ContextDir Data -OutputDir Models/Generated -ContextNamespace ContosoPizza.Data -Namespace ContosoPizza.Models

## A Big BUG
- ERROR: 自己引用自己

```
public partial class Customer
{
    public string FirstLast
    {
        //get => $"{FirstLast} {LastName}";   BIG BUG
        get => $"{FirstName} {LastName}";
    }
}

```




## make note on Program.cs
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
