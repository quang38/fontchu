
-------------------------------------------------------------------------------

## 1. Đăng ký font trong `es_extended/client/functions.lua`

```lua
-- Đăng ký font
RegisterFontFile('BalooPaaji2-SemiBold')       -- tên file .gfx

local balooFontId = RegisterFontId('Baloo Paaji 2 Semibold')       -- tên id font (để sau này dễ xài ở các src khác)

-- Lưu font vào ESX
CreateThread(function()
    ESX.FontId = balooFontId

    -- Đăng ký TextEntry toàn hệ thống
    AddTextEntry('STRING', "<FONT FACE='Baloo Paaji 2 Semibold'>~a~</FONT>")
    AddTextEntry('CUSTOM_STRING', "<FONT FACE='Baloo Paaji 2 Semibold'>~a~</FONT>")
    AddTextEntry('name', "<FONT FACE='Baloo Paaji 2 Semibold'>~a~</FONT>")
end)
```
----------------------------------------------------------------------
## 2. Đăng ký font bằng tay (đối vói 1 số loại bị lỗi ô vuông)
```lua
<FONT FACE='Baloo Paaji 2 Semibold'>test</FONT>
```
```lua
<FONT FACE="Baloo Paaji 2 Semibold">test</FONT>
```
