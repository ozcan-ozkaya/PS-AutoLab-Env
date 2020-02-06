# Lab Definition

This lab builds the following:

* 1 workgroup based server (S1) running Windows Server 2019 Core with an IP address of 192.168.3.19.
Administrator password is P@ssw0rd

## To get started

To run the full lab setup, which includes Setup-Lab, Run-Lab, Enable-Internet, and Validate-Lab. You should run all commands from the directory with the MOF and psd1 files.

```powershell
PS> Unattend-Lab
```

To run the commands individually to setup the lab environment:

Run the following for initial setup:

```powershell
PS> Setup-Lab
```

To start the Lab, and apply configurations the first time:

```powershell
PS> Run-Lab
```

To enable Internet access for the VM's, run:

```powershell
PS> Enable-Internet
```

To validate when configurations have converged:

```powershell
PS> Validate-Lab
```

Or you can run the Pester test directly

```powershell
PS> Invoke-Pester vmvalidate.test.ps1
```

## To Stop and snapshot the lab

To stop the lab VM's:

```powershell
PS> Shutdown-lab
```

To checkpoint the VM's:

```powershell
PS> Snapshot-Lab
```

To quickly rebuild the labs from the checkpoint, run:

```powershell
PS> Refresh-Lab
```

## To Patch a lab

If you want to make sure the virtual machines have the latest updates from Microsoft, you can run this command:

```powershell
PS> Update-Lab
```

Because this may take some time to run, you can also run it as a background job.

```powershell
PS> Update-Lab -asjob
```

## To remove a lab

To destroy the lab to build again run:

```powershell
PS> Wipe-Lab
```

You will be prompted for each virtual machine. Or you can force the removal and suppress the prompts:

```powershell
PS> Wipe-Lab -force
```