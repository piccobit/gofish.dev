---
title: "Install"
date: 2022-03-11
anchor: "install"
weight: 12
---

MacOS/Linux:

```bash
curl -fsSL https://raw.githubusercontent.com/tinned-fish/gofish/main/scripts/install.sh | bash
```

Windows (Powershell, as Administrator):

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force
iex ((New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/tinned-fish/gofish/main/scripts/install.ps1'))
```

After running one of the install scripts:

```bash
gofish init
```

Once you have GoFish up and running, you can upgrade at any time using

```bash
gofish install gofish
```

Then:

```bash
gofish upgrade gofish
```

{{% block note %}}
Please inspect the install scripts prior to running them to ensure your OS's safety. You should verify the security and contents of any script from the internet you are not familiar with.
{{% /block %}}
