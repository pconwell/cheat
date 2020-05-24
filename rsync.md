## Basic Syntax
> note that `/directory` and `/directory/` do different things:  
> `/directory` copies the files *inside* the directory  
> `/directory/` copies the directory itself  

rsync [options] source destination

## common options

```
-r recursive
-a archive (syncs recursively and preserves symbolic links, special and device files, modification times, group, owner, and permissions.)
-v verbose
-P progress
-z compress transfer (might not be beneficial on fast connections)
--delete delete files from destination if deleted from source (normally won't delete anything)
```

## examples

### copy files from `source` to `desination` with archive and compression
`rsync -azP /source/directory /destination/directory`

### copy and delete files (aka "mirror") between `source` and `destination`
`rsync -aP --delete /source/directory /destination/directory`

### copy files from local `source` to `ssh:destination`
`rsync -a /source/ username@remote_host:destination`

### copy files from `ssh:source` to local `destination`
`rsync -a username@remote_host:/source /destination`
