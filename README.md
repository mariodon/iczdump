# iczdump
Mirror of Iczelion's PE Dumper

IczDump (Iczelion's PE Dumper) is yet another in-memory Portable Executable File dumper. However, it's different in subtle ways from other dumpers: it runs in the same process as the target because it's a DLL. Once the DLL is in a process, it has the same privilege as the the target. It can:

* dump file structures: DOS & PE headers, sections, resources
* do custom dump: let you specify the address range you want to dump
* suspend-resume primary thread of the process
* edit the in-memory PE structures
* reload PE headers from the target
* display module list: list all modules in the process. You can load/unload modules.
* select target module to examine,dump via the module list
* search the target for import table
* search the target for thunk dwords (import function addresses)
* do Import Address Table (IAT) query
Furthermore, it's difficult to detect because it doesn't use win32 debug api or any ring-0 tracer. Just about the only way it can be detected is for the target to scan the whole process for it and if that occurs, we can find ways of avoiding the detection.
