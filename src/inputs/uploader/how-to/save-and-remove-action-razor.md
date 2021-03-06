---
title: "Save and Remove action in ASP.NET Core Razor"
component: "Uploader"
description: "Explain Server-side configuration for save and remove action of the file upload control."
---

# Save and Remove action in ASP.NET Core Razor

The save action handler upload the files that needs to be specified in the [saveUrl](https://help.syncfusion.com/cr/aspnetcore-js2/Syncfusion.EJ2.Inputs.UploaderAsyncSettings.html#Syncfusion_EJ2_Inputs_UploaderAsyncSettings_SaveUrl) property.
The save handler receives the submitted files and manages the save process in server.

{% aspTab template="uploader/razor-save" %}

{% endaspTab %}

## Server-side configuration for startup page

This section explains how to add the anti forgery tokens header in `startup` page.

```csharp

public void ConfigureServices(IServiceCollection services)  
{  
    services.AddMvc().AddJsonOptions(x =>  
    {  
        x.SerializerSettings.ContractResolver = new DefaultContractResolver();  
    });  
    services.AddAntiforgery(o => o.HeaderName = "xsrf-token");  
}

```

## Server-side configuration for save action

This section explains how to handle the server-side action for saving the file from server.

```csharp
private IHostingEnvironment hostingEnv;

public UploaderController(IHostingEnvironment env)
{
    this.hostingEnv = env;
}

 [AcceptVerbs("Post")]  
public IActionResult OnPostSave(IList<IFormFile> UploadFiles)  
{  
    try  
    {  
        foreach (var file in UploadFiles)  
        {  
            if (UploadFiles != null)  
            {  
                var filename = ContentDispositionHeaderValue.Parse(file.ContentDisposition).FileName.Trim('"');  
                filename = hostingEnv.WebRootPath + $@"\{filename}";  
                if (!System.IO.File.Exists(filename))  
                {  
                    using (FileStream fs = System.IO.File.Create(filename))  
                    {  
                        file.CopyTo(fs);  
                        fs.Flush();  
                    }  
                }  
                else  
                {  
                    Response.Clear();  
                    Response.StatusCode = 204;  
                    Response.HttpContext.Features.Get<IHttpResponseFeature>().ReasonPhrase = "File already exists.";  
                }  
            }  
        }  
    }  
    catch (Exception e)  
    {  
        Response.Clear();  
        Response.ContentType = "application/json; charset=utf-8";  
        Response.StatusCode = 204;  
        Response.HttpContext.Features.Get<IHttpResponseFeature>().ReasonPhrase = "No Content";  
        Response.HttpContext.Features.Get<IHttpResponseFeature>().ReasonPhrase = e.Message;  
    }  
    return Content("");  
}

```

## Server-side configuration for remove action

This section explains how to handle the server-side action for removing the file from server.

```csharp

private IHostingEnvironment hostingEnv;

public HomeController(IHostingEnvironment env)
{
    this.hostingEnv = env;
}
[AcceptVerbs("Post")]  
public IActionResult OnPostRemove(IList<IFormFile> UploadFiles)  
{  
    try  
    {  
        foreach (var file in UploadFiles)  
        {  
            var fileName = ContentDispositionHeaderValue.Parse(file.ContentDisposition).FileName.Trim('"');  
            var filePath = Path.Combine(hostingEnv.WebRootPath);  
            var fileSavePath = filePath + "\\" + fileName;  
            if (!System.IO.File.Exists(fileSavePath))  
            {  
                System.IO.File.Delete(fileSavePath);  
            }  
        }  
    }  
    catch (Exception e)  
    {  
        Response.Clear();  
        Response.StatusCode = 200;  
        Response.HttpContext.Features.Get<IHttpResponseFeature>().ReasonPhrase = "File removed successfully";  
        Response.HttpContext.Features.Get<IHttpResponseFeature>().ReasonPhrase = e.Message;  
    }  
    return Content("");  
}  

```