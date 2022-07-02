# Temporary-Files-Remover
This is a python script embed with a `data.json` file which will help you in removing any temporary files you want. It basically will delete every file inside your temporary folder based on your customized settings. If you wish the code to run faster, then make sure that your temporary files folder is in your default disk, in most cases it is the `C:\` disk.

Customizing the `data.json` file:

This is the default view of the file:
{"folder_name": "temp-files", "folder_location": "", "directory": "", "delDelay": "86400"}

Key Values:
The "folder_name" is the name of your temporary folder with the default value `temp-files` as the name. *Note that the code will only look for the first folder to make it run faster*
The "folder_location" is the location of your folder which the code will find it based on your folder name. *It is highly recommended to not alter this field*
The "directory" is a list of all your disks in the system which will be filled when you run the code. *It is highly recommend to not alter this field*
The "delDelay" is the time duration in seconds with the default value `86400` or `1 day` for which you want every file in the temporary folder to be deleted after.

However it is highly recommended to not alter the `.json` file for a better performance without any errors.

How to Understand the `logs.log` file:
This file is basically the place where every action of the code will be written *not including the editing of the `data.json` file*

Different Log Readings:

**CRITICAL:** This is just the log indicating that a file in the temporary folder has been deleted. *Even from the recycle bin, put in less efforts*
**DEBUG:** This log type means there was a problem in one of the Key Values and has been restored to default.
**ERROR:** This is an error meaning one of the Key Values has not been found/is incorrect. *However if there is a "folder_location" value then usually the error won't be thrown. In such cases, reset the "folder_location" to `""` for checking if your temporary file exists or not. In Error Logs, the code doesn't restore values, to avoid further errors, thus it is to be done manually*
**INFO:** This is just an information indicating that the code is on and running well. *Unless you do some mischieve with it*
**WARNING:** This is just a warning indicating that you misentered/altered a value in the `data.json` incorrectly. *In most cases the values are restored to default, and if not then it is highly recommend to restore them to the default. If you don't know what the default values are, just overwrite the whole `data.json` file to `{}`.*

Here's an example of all the logs:

**INFO:**
The temp-file-checker file is now on and working. All logs will come up here!
Time: 07/02/22, 14:02:21

**ERROR:**
No directory found with the name 'test-dir'
Time: 07/02/22, 14:02:21

**WARNING:**
A proper format for delDelay in seconds wasn't entered. A default value of 86400s has been restored.
Value Entered: test-value
Time: 07/02/22, 14:02:38

**DEBUG:**
Restored the default folder_name.
Old: \invalid-file\
Current: temp-files
Time: 07/02/22, 14:02:45

**DEBUG:**
Restored the default data.json blueprint.
Time: 07/02/22, 14:03:56

**CRITICAL:**
File Removed: C:\\temp-files\test-file.txt
Date Modified: 07/02/22, 14:05
Date Deleted: 07/02/22, 14:05:22

Self Error Handling:
If the `data.json` file is empty, then you need to make it an empty json file. Meaning, just type `{}` and save it, then the code should function properly.


