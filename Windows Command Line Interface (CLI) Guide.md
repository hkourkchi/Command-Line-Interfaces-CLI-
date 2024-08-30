# Windows Command Line Interface (CLI) Guide

## 1. Navigation Commands

- **`cd [directory]`**: Changes the current directory to the specified directory.
  ```cmd
  cd C:\Users\YourUsername\Documents
  ```

- **`dir`**: Lists the files and directories in the current directory.
  ```cmd
  dir
  ```

- **`echo %cd%`**: Displays the current working directory.
  ```cmd
  echo %cd%
  ```

## 2. File and Directory Management

- **`copy [source] [destination]`**: Copies files from the source to the destination.
  ```cmd
  copy file.txt C:\Users\YourUsername\Documents
  ```

- **`move [source] [destination]`**: Moves or renames files or directories.
  ```cmd
  move oldname.txt newname.txt
  ```

- **`del [filename]`**: Deletes a file.
  ```cmd
  del file.txt
  ```

- **`rmdir [directory]`**: Removes a directory. Use `rmdir /s [directory]` to remove a directory and its contents.
  ```cmd
  rmdir directory_name
  rmdir /s directory_name
  ```

- **`mkdir [directory]`**: Creates a new directory.
  ```cmd
  mkdir newfolder
  ```

## 3. Viewing and Editing Files

- **`type [filename]`**: Displays the contents of a file.
  ```cmd
  type file.txt
  ```

- **`notepad [filename]`**: Opens a file in Notepad.
  ```cmd
  notepad file.txt
  ```

- **`edit [filename]`**: Opens a file in the built-in text editor (deprecated in newer versions).
  ```cmd
  edit file.txt
  ```

## 4. Permissions and Ownership

- **`icacls [filename] /grant [username]:[permissions]`**: Changes the file permissions.
  ```cmd
  icacls file.txt /grant UserName:F
  ```

- **`takeown /f [filename]`**: Takes ownership of a file or directory.
  ```cmd
  takeown /f file.txt
  ```

## 5. Process Management

- **`tasklist`**: Displays the currently running processes.
  ```cmd
  tasklist
  ```

- **`taskkill /PID [PID]`**: Terminates a process by its Process ID (PID).
  ```cmd
  taskkill /PID 1234
  ```

- **`taskkill /IM [process_name]`**: Terminates all processes with the specified name.
  ```cmd
  taskkill /IM notepad.exe
  ```

## 6. Networking

- **`ping [host]`**: Sends ICMP echo requests to a network host.
  ```cmd
  ping google.com
  ```

- **`ipconfig`**: Displays network configuration information.
  ```cmd
  ipconfig
  ```

- **`tracert [host]`**: Traces the route to a network host.
  ```cmd
  tracert google.com
  ```

- **`curl [url]`**: Fetches data from a URL.
  ```cmd
  curl http://example.com
  ```

## 7. System Information

- **`systeminfo`**: Displays detailed information about the system.
  ```cmd
  systeminfo
  ```

- **`wmic logicaldisk get size,freespace,caption`**: Shows disk space usage.
  ```cmd
  wmic logicaldisk get size,freespace,caption
  ```

- **`taskmgr`**: Opens the Task Manager.
  ```cmd
  taskmgr
  ```

## 8. Searching

- **`dir [pattern] /s`**: Searches for files matching the pattern in the current directory and subdirectories.
  ```cmd
  dir *.txt /s
  ```

- **`findstr [pattern] [file]`**: Searches for a specific pattern in a file.
  ```cmd
  findstr "hello" file.txt
  ```

## 9. Archiving and Compression

- **`tar -cf [archive_name.tar] [directory]`**: Creates a `.tar` archive (available in Windows 10 and later).
  ```cmd
  tar -cf archive.tar C:\Users\YourUsername\Documents
  ```

- **`tar -xf [archive_name.tar]`**: Extracts a `.tar` archive.
  ```cmd
  tar -xf archive.tar
  ```

- **`compact /c [filename]`**: Compresses a file or directory.
  ```cmd
  compact /c file.txt
  ```

- **`compact /u [filename]`**: Decompresses a file or directory.
  ```cmd
  compact /u file.txt
  ```

## 10. User Management

- **`net user [username] /add`**: Adds a new user.
  ```cmd
  net user newuser /add
  ```

- **`net user [username] [password]`**: Changes the password for a user.
  ```cmd
  net user newuser newpassword
  ```

- **`runas /user:[username] [command]`**: Runs a command with the specified user account.
  ```cmd
  runas /user:Administrator cmd
  ```

- **`shutdown /s /t [seconds]`**: Shuts down the computer after a specified number of seconds.
  ```cmd
  shutdown /s /t 60
  ```


# Specialized Windows CLI Commands for File and Folder Management

| **Function**                           | **Command**                                          | **Description**                                              |
|----------------------------------------|------------------------------------------------------|--------------------------------------------------------------|
| **List Files and Directories**         | `dir`                                                | Lists all files and directories in the current directory.   |
| **Change Directory**                   | `cd [directory]`                                    | Changes the current directory to the specified directory.   |
| **Display Current Directory**          | `echo %cd%`                                          | Displays the current working directory.                     |
| **Create New Directory**               | `mkdir [directory]`                                | Creates a new directory.                                    |
| **Remove Empty Directory**             | `rmdir [directory]`                                | Removes an empty directory.                                 |
| **Remove Directory and Contents**      | `rmdir /s [directory]`                             | Removes a directory and all of its contents.                |
| **Copy File**                          | `copy [source] [destination]`                       | Copies a file from the source to the destination.           |
| **Copy Directory and Contents**        | `xcopy [source] [destination] /s /e`                | Copies a directory and its contents, including subdirectories. |
| **Move File**                          | `move [source] [destination]`                       | Moves or renames a file.                                    |
| **Move Directory and Contents**        | `move [source] [destination]`                       | Moves or renames a directory and its contents.              |
| **Delete File**                        | `del [filename]`                                    | Deletes a specified file.                                   |
| **Delete Multiple Files**              | `del [pattern]`                                    | Deletes multiple files matching the specified pattern.      |
| **Delete Directory and Contents**      | `rd /s [directory]`                                | Removes a directory and all of its contents (alias for `rmdir /s`). |
| **Rename File or Directory**           | `ren [oldname] [newname]`                           | Renames a file or directory.                                |
| **Find Files and Directories**         | `dir [pattern] /s`                                | Searches for files and directories matching the pattern in the current directory and subdirectories. |
| **Search Text in Files**               | `findstr [pattern] [file]`                          | Searches for a specific text pattern in a file.             |
| **Display File Content**               | `type [filename]`                                  | Displays the contents of a file.                            |
| **Compare Files**                     | `fc [file1] [file2]`                                | Compares two files and displays the differences.            |
| **Create Archive**                    | `tar -cf [archive_name.tar] [directory]`            | Creates a `.tar` archive of a directory (Windows 10+).       |
| **Extract Archive**                   | `tar -xf [archive_name.tar]`                        | Extracts a `.tar` archive (Windows 10+).                    |
| **Compress File**                     | `compact /c [filename]`                            | Compresses a file or directory.                             |
| **Decompress File**                   | `compact /u [filename]`                            | Decompresses a file or directory.                           |
| **Copy Directory Tree**               | `robocopy [source] [destination] /e`                | Copies a directory tree with all subdirectories and files.  |
| **Get File Attributes**               | `attrib [filename]`                                | Displays or changes the attributes of a file.               |
| **Set File Attributes**               | `attrib +[attribute] [filename]`                    | Sets specified attributes for a file.                       |


