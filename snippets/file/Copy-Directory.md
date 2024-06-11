# Copy Directory
Copies the content of an directory to another directory. This will create the target directory if it does not exist.

```kt
fun copyDirectory(source: File, destination: File) {
        source.walk().forEach { src ->
            val target = File(destination, source.toPath().relativize(src.toPath()).toString())
            if (src.isDirectory) {
                target.mkdirs()
            } else {
                src.copyTo(target, overwrite = true)
            }
        }
    }
```