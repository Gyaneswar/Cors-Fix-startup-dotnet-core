# Cors-Fix-startup-dotnet-core-web-api

##inside cofigureServices add this code. And change the link accordingly.
            
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
