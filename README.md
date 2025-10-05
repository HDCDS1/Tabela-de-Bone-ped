> # Metodo usado

```lua
ffi = require"ffi"
ffi.cdef([[
    //ConvertBoneTag2BoneName(int) 32 & 64 bits
    const char* _Z23ConvertBoneTag2BoneNamei(int);
]])
newt = ffi.new"char[256]"
for idbone = 0, 302 do
    local cname = ffi.load"GTASA"._Z23ConvertBoneTag2BoneNamei(idbone)
    if cname ~= ffi.NULL then
        ffi.copy(newt,cname, 256)
        print(idbone,ffi.string(newt))
    end
end
```

### [````Accessing Standard System Functions````](https://luajit.org/ext_ffi_tutorial.html)
### [````Utility Functions````](https://luajit.org/ext_ffi_api.html)
### [````Conhecendo FFI e Trabalhando com Memória em Lua````](https://www.blast.hk/threads/196541/)
