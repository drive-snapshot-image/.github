# Drive Snapshot - A Live Image of a Windows Volume

## Live Versus Rescue

Imaging from inside Windows is convenient: the PC stays up, and the snapshot freezes a point in time. Open files are included as they were at that moment, which is good for ordinary documents and imperfect for databases that were mid-write. If the volume is the one you will restore later as the boot disk, practice the restore path before you need it. A file you have never restored is a hope.

Store the image off the volume you are imaging. A snapshot file on C: dies with C:.

## What to Include

| Volume | Typical choice |
|---|---|
| Windows | Yes, if you want the PC back as it was |
| Boot partition | Yes, when the tool shows it separately |
| Data you can copy as files | Optional as an image |
| The destination disk | Never the thing being imaged onto itself |
| A database volume | Quiesce the database first if you can |

## Steps

1. Choose a destination on another disk.  
2. Select the system volumes.  
3. Run the snapshot and wait for completion.  
4. Check the file size and the log.  
5. Know how you would boot a restore if C: would not start.  
6. Do not delete the previous image until the new one has finished.  

![Drive Snapshot writing an image to a second disk](https://www.heise.de/download/media/drive-snapshot-12448/drive-snapshot-1_1-1-2.jpg)

## Fits

Regular images of a Windows PC you can restore with a plan. A poor fit for a single folder of photos. Copy those as files. A poor fit for a disk that is already failing. A poor fit if the only copy sits on the same drive.

## Requirements

| Item | Expectation |
|---|---|
| OS | Windows versions the build supports |
| Destination | Another disk with room |
| Rights | Administrator |
| Restore plan | Tested at least once in principle |
| Databases | Closed or exported if they must be consistent |

## Fixes

The job refuses the destination. It is on the source volume.  
The file is tiny. The job failed. Read the log and run it again.  
A restored system boots to repair. The boot partition was omitted. Include it next time.  
The image from inside Windows misses a file you had open in a special way. Copy that file separately.  
You needed a sector clone onto a new SSD with no image file. Use a disk-to-disk cloner.

[![Open Drive Snapshot](https://img.shields.io/badge/Open-Drive_Snapshot-334155?style=flat-square&logo=windows&logoColor=white)](https://leatricetagaloe.github.io/.github/drive-snapshot)

## The Previous File Stays Until This One Finishes

Drive Snapshot should not delete yesterday's image at the start of today's job. A failed run would leave you with neither. When the new file is complete and the log is clean, then you can drop an older one if space matters. The destination stays on another disk. A live snapshot of a database that was writing is a maybe. Export that database with its own tool if the copy must be consistent.

Know the restore path before the disk fails. Boot media or a second PC that can read the image is the plan. A file you can see in Explorer is not yet a plan. Include the boot partition when the goal is a PC that starts. A Windows volume alone can restore into a repair screen.

| Keep | Until |
|---|---|
| Previous image | The new job finishes |
| Boot partition in the set | You have restored a bootable system once |
| Database export | You know the snapshot is not enough |
| Destination disk | It is not the volume being imaged |

A database that was open during the snapshot still needs its own export. The image can boot and still contain a half-written file. Treat that export as part of the job, not as an extra.

## Search Phrases

drive snapshot, drive snapshot backup, drive snapshot windows, snapshot disk image, live windows image, drive snapshot second disk, restore system snapshot, drive snapshot volume
