# SQL Server Disc Sector Size Greater Than 4KB Error Fix for Windows 11 and Windows Server 2022
This repository provides Windows command files for fixing errors related to system disk sector sizes greater than 4 KB during installation or starting an instance of SQL Server on Windows 11 and Windows Server 2022. These patches are valid for all released versions of SQL Server.

## Files Anatomy
### <a href="Check.cmd">Check.cmd</a>
if <code>PhysicalBytesPerSectorForAtomicity</code> and <code>PhysicalBytesPerSectorForPerformance</code> reports values exceeding 4096 after running this file, a system patch will be needed.
### <a href="Patch.cmd">Patch.cmd</a>
This file enables emulation of the required 4-KB sector size required by Windows by setting <code>PhysicalBytesPerSectorForAtomicity</code> and <code>PhysicalBytesPerSectorForPerformance</code> to a value of 4096. After running this file, a system restart will be needed to reflect changes.
### <a href="Rollback.cmd">Rollback.cmd</a>
This file reverts back changes made by patching. After running this file, a system restart will be needed to reflect changes.
### <a href="Validate.cmd">Validate.cmd</a>
This file confirms if changes were successful after patching by running a query on changed values.

## Author
Seif Elden Abu El-Ela
