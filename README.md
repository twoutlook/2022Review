# 2022Review

## 04/04
### Beginners ASP.NET Core Identity Tutorial
- Code with Julian 
- 2.13K subscribers
- https://www.youtube.com/watch?v=5UfJeDcoC1k
#### Review
- NuGet CodeGeneration.Design
- Add -> New Scaffolded Item
- 他選了 layout , 多此一舉, 結果 bootstrap 功能異常
- 承上, 實驗了直接使用預設值是OK的

### ASP.NET Identity with Identity Server 4 | Tutorial Part 1
- https://www.youtube.com/watch?v=SXJ377G5bOg

#### Review
- NuGet EntityFrameworkCore.SqlServer 及 Tools, 教程分開在 API 及 DataAccess 分別加上。
  - 其實可以以 Solutions 的方式, 兩個project 一起加上。一則是整體性省時間; 另一則是容易版本的異差, 這個在舊專案沒有適當升級很容易體現出來。
#### Troubeshot
- 28:54, 跟著做時 API|Dependencies|Projects|DataAccess 裡是空的, 運行時會報錯
  - System.IO.FileNotFoundException: 'Could not load file or assembly 'DataAccess, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null'. The system cannot find the file specified.'
-  但是取 https://github.com/iulianoana/CoffeeShopper-IS4
  - git branch -a
  - git checkout Part1-Setting_Up_The_API 
  - 改了 API appsettings.json
  ```
      "ConnectionStrings": {
        "DefaultConnection": "Server=.;Database=CoffeeShopperDbV0;Trusted_Connection=True"
    }
  
  ```
  - Developer PowerShell: for both API and DataAccess, dotnet restore
  - Package Managere Console: Update-Database
  - API|Dependencies|Projects|DataAccess 有 Microsoft.EntityFrameworkCore.SqlServer(6.0.1)
#### Troubeshot 結果
- 將 EntityFrameworkCore.SqlServer 由 6.0.3 降到 6.0.1 居然可以了, 就是看到 API|Dependencies|Projects|DataAccess 有 Microsoft.EntityFrameworkCore.SqlServer(6.0.1)
