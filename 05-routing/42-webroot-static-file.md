- default is `wwwroot`
  - only files in this folder is accessible for security
- can configure

  ```
  var builder = WebApplication.CreateBuilder(new WebApplicationOptions(){
    WebRootPath = "myroot"
  });
  ```

- expose multiple folders

  ```
  app.UseStaticFiles(); // works with root1 path

  app.UseStaticFiles(new StaticFileOptions(){
    FileProvider = new PhysicalFileProvider(
        Path.Combine(builder.Environment.ContentRootPath, "mywebroot");
    );
  }); // works with root2 path
  ```
