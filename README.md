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

## References

[Asciidoctor](https://asciidoctor.org/)

[Building Blog With Asciidoc](http://millross-consultants.com/building_blog_with_asciidoc.html)
