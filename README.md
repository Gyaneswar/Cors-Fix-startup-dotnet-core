# Cors-Fix-startup-dotnet-core

           
   ##inside cofigureServices add this code
            
   ```
   services.AddCors(options =>
   {
       options.AddPolicy(name: MyAllowSpecificOrigins,
                         builder =>
                         { 
                             builder.WithOrigins("http://localhost:4200");
                         });
   });
   ```



   ##after app.UseRouting() in configure method add this line
   
   ```
   app.UseCors(MyAllowSpecificOrigins);
   ```
