Custom Plugins for the Lunar Package Management System
------------------------------------------------------

verify-addchecksum.plugin
~~~~~~~~~~~~~~~~~~~~~~~~~

Install by copying the file to /var/lib/lunar/plugins.

Now, every time you download a source file of a package
and the package's `DETAILS` file does not provide a checksum, i.e.,
the file contains a line

> SOURCE\d*_VFY=

or

> SOURCE\d*_VFY=sha256:

instead of a valid entry, the plugin will automatically fill in
the checksum of the downloaded file before discarding the file.

The plugin also supports packages with custom definitions for different architectures
(`DETAILS.$PLATFORM`), but keep in mind that only your own platform version will be updated automatically.

Please still verify the checksums against values provided by upstream together with the release!
There have been sufficient cases of intentional or accidental data manipulation in the past.
