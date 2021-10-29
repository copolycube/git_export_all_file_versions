# git-history

from : https://stackoverflow.com/questions/12850030/git-getting-all-previous-version-of-a-specific-file-folder


The script would:

*    extract all file versions to /tmp/all_versions_exported
*    take 1 argument - relative path to the file inside git repo
*    give result filenames numeric prefix (sortable)
*    mention inspected filename in result files (to tell apples apart from oranges:)
*    mention commit date in the result filename (see output example below)
*    not create empty result files


 Usage example:

```
cd /home/myname/my-git-repo

git_export_all_file_versions docs/howto/readme.txt
    result stored to /tmp/all_versions_exported

ls /tmp/all_versions_exported
    0001.17-Oct-2016.ee0a1880ab815fd8f67bc4299780fc0b34f27b30.readme.txt
    0002.3-Oct-2016.d305158b94bedabb758ff1bb5e1ad74ed7ccd2c3.readme.txt
    0003.29-Sep-2016.7414a3de62529bfdd3cb1dd20ebc1a977793102f.readme.txt
    0004.28-Sep-2016.604cc0a34ec689606f7d3b2b5bbced1eece7483d.readme.txt
    0005.28-Sep-2016.198043c219c81d776c6d8a20e4f36bd6d8a57825.readme.txt
    0006.9-Sep-2016.5aea5191d4b86aec416b031cb84c2b78603a8b0f.readme.txt
    <and so on and on . . .>
```

```
$ git_export_all_file_versions bin/git_export_all_file_versions /tmp/stackoverflow/demo
Creating directory '/tmp/stackoverflow/demo'
Writing files to '/tmp/stackoverflow/demo'
...

$ ls -1 /tmp/stackoverflow/demo/
2017-05-02T15:52:52-04:00.c72640ed968885c3cc86812a2e1aabfbc2bc3b2a.git_export_all_file_versions
2017-05-02T16:58:56-04:00.bbbcff388d6f75572089964e3dc8d65a3bdf7817.git_export_all_file_versions
2017-05-02T17:05:50-04:00.67cbdeab97cd62813cec58d8e16d7c386c7dae86.git_export_all_file_versions
```

edit: if you see errors like this:
```
    fatal: Not a valid object name 3e93eba38b31b8b81905ceaa95eb47bbaed46494:readme.txt
```

it means you've started the script not from the root folder of your git project.
edited Jul 15 at 0:34

    The previously provided accepted answer (@sehe) did not indeed perform directly the retrieval of ALL versions at once. As mentionned in the comment I used the both command to build a java program (not a general solution that could be uploaded as is) that did it. Your solution is better as it gives the end result of my past java program. – 
    max152
    Jan 30 '17 at 9:51 

This script works, but there are a few issues and possibly-unexpected behaviors. Please see my answer for details and an updated script. – 
Nathan Arthur
