# Third-Party Notices

This application uses the following third-party packages, embedded into the
built exe via [Costura.Fody](https://github.com/Fody/Costura). This file
lists them along with their licenses, as a courtesy alongside the terms of
the [LGPL-2.1 license](LICENSE) this project itself is under.

## NvAPIWrapper.Net
- **License:** LGPL-3.0
- **Source:** https://github.com/falahati/NvAPIWrapper
- Used unmodified, as a library dependency, to call NVIDIA's Digital
  Vibrance (DVC) API. Its full license text is available at the link
  above and applies to that library's own source.

## Newtonsoft.Json
- **License:** MIT
- **Source:** https://github.com/JamesNK/Newtonsoft.Json
- Copyright (c) 2007 James Newton-King

## Fody / Costura.Fody
- **License:** MIT
- **Source:** https://github.com/Fody/Fody, https://github.com/Fody/Costura
- Build-time IL weaver used to embed the dependencies below into a single
  exe; Costura's small runtime assembly-resolving helper ships inside the
  built exe.

## Microsoft.Extensions.* (Configuration, FileProviders, FileSystemGlobbing, Primitives)
- **License:** MIT
- **Source:** https://github.com/dotnet/runtime
- Copyright (c) .NET Foundation and Contributors

## BCL compatibility packages (System.*, NETStandard.Library, Microsoft.NETCore.Platforms, Microsoft.Win32.Primitives)
- **License:** MIT
- **Source:** https://github.com/dotnet/corefx, https://github.com/dotnet/standard
- Copyright (c) .NET Foundation and Contributors
- These are the small polyfill packages that let this .NET Framework 4.7.2
  app use newer BCL APIs; listed as a group since there are dozens of them
  (see `packages.config` for the full, exact list with versions).
