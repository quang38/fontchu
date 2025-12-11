## `ESX`

-------------------------------------------------------------------------------
## 1. Đăng ký font trong `es_extended/client/functions.lua`
-------------------------------------------------------------------------------

```lua
-- Đăng ký font
-- tên file .gfx
RegisterFontFile('BalooPaaji2-SemiBold') 
-- tên id font (để sau này dễ xài ở các src khác)
local balooFontId = RegisterFontId('Baloo Paaji 2 Semibold')

-- Lưu font vào ESX
CreateThread(function()
    ESX.FontId = balooFontId
    -- Đăng ký TextEntry toàn hệ thống
    AddTextEntry('STRING', "<FONT FACE='Baloo Paaji 2 Semibold'>~a~</FONT>")
    AddTextEntry('CUSTOM_STRING', "<FONT FACE='Baloo Paaji 2 Semibold'>~a~</FONT>")
    AddTextEntry('name', "<FONT FACE='Baloo Paaji 2 Semibold'>~a~</FONT>")
end)
```
-------------------------------------------------------------------------------
## 2. Đăng ký font bằng tay (đối vói 1 số loại bị lỗi ô vuông)
-------------------------------------------------------------------------------
```lua
<FONT FACE='Baloo Paaji 2 Semibold'>test</FONT>
```
hoặc
```lua
<FONT FACE="Baloo Paaji 2 Semibold">test</FONT>
```
-------------------------------------------------------------------------------

## `QB CORE`

-------------------------------------------------------------------------------
## 1. Đăng ký font trong `es_extended/client/functions.lua`
-------------------------------------------------------------------------------

```lua
CreateThread(function()
	RegisterFontFile('Oswald') -- the name of your .gfx, without .gfx
	QBCore.FontId = RegisterFontId('Oswald') -- the name from the .xml
	AddTextEntry('STRING', "<FONT face='Oswald'>~a~</FONT>")
	AddTextEntry('CUSTOM_STRING', "<FONT face='Oswald'>~a~</FONT>")
	
	while true do
		Wait(0)
		local currTime = GetGameTimer()

		for i=1, #QBCore.TimeoutCallbacks, 1 do
			if QBCore.TimeoutCallbacks[i] then
				if currTime >= QBCore.TimeoutCallbacks[i].time then
					QBCore.TimeoutCallbacks[i].cb()
					QBCore.TimeoutCallbacks[i] = nil
				end
			end
		end
	end
end)

```
-------------------------------------------------------------------------------
## 2. Đăng ký font bằng tay (đối vói 1 số loại bị lỗi ô vuông)
-------------------------------------------------------------------------------
```lua
<FONT FACE='Oswald'>test</FONT>
```
hoặc
```lua
<FONT FACE="Oswald">test</FONT>
```
-------------------------------------------------------------------------------
