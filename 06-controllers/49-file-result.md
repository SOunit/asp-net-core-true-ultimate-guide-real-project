# File results

- VirtualFileResult
- PhysicalFileResult
- FileContentResult

# VirtualFileResult

- if file is in wwwroot

```
[Route("file-download")]
public VirtualFileResult FileDownload(){
    // file path, MIME type
    return new VirtualFileResult("/sample.pdf", "application/pdf");
}
```

# PhysicalFileResult

- if the file is outside the project

```
[Route("file-download")]
public PhysicalFileResult FileDownload(){
    // absolute path, MIME type
    return new PhysicalFileResult(@"c:\aspnetcore\sample.pdf", "application/pdf");
}
```

# FileContentResult

- if file is byte[]

```
[Route("file-download")]
public FileContentResult FileDownload(){
    byte[] bytes = System.IO.File.ReadAllBytes(@"c:\aspnet\sample.pdf");

    return new FileContentResult(bytes, "application/pdf");
}
```