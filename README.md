# Asciidoctor Sample Blog

This is a sample project to built a blog with Asciidoctor in windows environment.

## Installation steps - Windows

Install Chocolatey package manager
```
 @"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
 ```

Install Ruby
```
choco install ruby -y
refreshenv
gem install bundler
```

Install Asciidoctor

```
gem install asciidoctor
```

## Conversion to HTML
```
asciidoctor --destination-dir web **/*.adoc
```
To include content from a URI the attribute `allow-uri-read`must be specified. More details can be found on [Include Content from a URI](##include-content-from-a-URI) section.
```
asciidoctor -a allow-uri-read --destination-dir web **/*.adoc
```


## Add CodeRay syntax highlighter

In order to use CodeRay with Asciidoctor, you need the coderay RubyGem. You can use one of the following methods to install CodeRay.

Install using gem (all systems)
```
gem install coderay
``` 

Verify `coderay`installation:
```
coderay -v 
```

Assign the coderay value to the source-highlighter attribute in the document header to activate it.
```
:source-highlighter: coderay
```


## Include content from a URI 
The include directive recognizes when the target is a URI and can include the content referenced by that URI.

This example demonstrates how to include an AsciiDoc file from a GitHub repo directly into your document.
```
include::https://raw.githubusercontent.com/asciidoctor/asciidoctor/master/README.adoc[]
```
For security reasons, this capability is not enabled by default. To allow content to be read from a URI, you must enable the URI read permission by:

running Asciidoctor in SERVER mode or less and setting the allow-uri-read attribute securely (i.e., from the CLI or API).

Here’s an example that shows how to run Asciidoctor from the console so it can read content from a URI:

```
asciidoctor -a allow-uri-read filename.adoc
```

## References

[Asciidoctor](https://asciidoctor.org/)

[Building Blog With Asciidoc](http://millross-consultants.com/building_blog_with_asciidoc.html)
