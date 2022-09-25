local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("MPS HUB", "DarkTheme")

--BIGFOOT AND AUTOCATCH

local Tab = Window:NewTab("Bigfoot/Ac")
local Section = Tab:NewSection("BestScript")

Section:NewButton("I Didn't Make This", "Made by yanros74", function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/AvexcitalScripts/thing/main/Protected", true))()
end)

local Section = Tab:NewSection("Right Leg")

Section:NewButton("Enable", "Made by yanros74", function()
game.Players.LocalPlayer.Character["Right Leg"].Massless = true
game.Players.LocalPlayer.Character["Right Leg"].Size = Vector3.new(3.2, 2, 5.1)
game.Players.LocalPlayer.Character["Right Leg"].Transparency = 0.6
end)

Section:NewButton("Disable", "Made by yanros74", function()
game.Players.LocalPlayer.Character["Right Leg"].Massless = true
game.Players.LocalPlayer.Character["Right Leg"].Size = Vector3.new(1.0, 2, 1.0)
game.Players.LocalPlayer.Character["Right Leg"].Transparency = 0
end)

local Section = Tab:NewSection("Ez Bigfoot")

Section:NewButton("Open with K Close with L", "Made by yanros74", function()
local plr = game:GetService("Players").LocalPlayer

game:GetService("UserInputService").InputBegan:Connect(function(Input)
if Input.KeyCode == Enum.KeyCode.K then -- change the keycode
local RIGHTLEGSIZE = Vector3.new(3.2,2,5.1) -- Default: 1,2,1
game.Players.LocalPlayer.Character["Right Leg"].Transparency = 0.6

plr.Character["Right Leg"].Size = RIGHTLEGSIZE
end
end)

game:GetService("UserInputService").InputBegan:Connect(function(Input)
if Input.KeyCode == Enum.KeyCode.L then -- Chnage the keycode
local RIGHTLEGSIZE = Vector3.new(1,2,1) -- Default: 1,2,1
game.Players.LocalPlayer.Character["Right Leg"].Transparency = 0

plr.Character["Right Leg"].Size = RIGHTLEGSIZE

end
end)
end)

local Section = Tab:NewSection("Left Leg")

Section:NewButton("Enable", "Made by yanros74", function()
game.Players.LocalPlayer.Character["Left Leg"].Massless = true
game.Players.LocalPlayer.Character["Left Leg"].Size = Vector3.new(3.2, 2, 5.1)
game.Players.LocalPlayer.Character["Left Leg"].Transparency = 0.6
end)

Section:NewButton("Disable", "Made by yanros74", function()
game.Players.LocalPlayer.Character["Left Leg"].Massless = true
game.Players.LocalPlayer.Character["Left Leg"].Size = Vector3.new(1.0, 2, 1.0)
game.Players.LocalPlayer.Character["Left Leg"].Transparency = 0
end)

local AUTOCATCHSection = Tab:NewSection("Right Hand")

AUTOCATCHSection:NewButton("Enable", "Made by yanros74", function()
game.Players.LocalPlayer.Character["Right Arm"].Massless = true
game.Players.LocalPlayer.Character["Right Arm"].Size = Vector3.new(30, 35, 1)
game.Players.LocalPlayer.Character["Right Arm"].Transparency = 0.9

end)

AUTOCATCHSection:NewButton("Disable", "Made by yanros74", function()
game.Players.LocalPlayer.Character["Right Arm"].Massless = true
game.Players.LocalPlayer.Character["Right Arm"].Size = Vector3.new(1, 2, 1)
game.Players.LocalPlayer.Character["Right Arm"].Transparency = 0

end)

local AUTOCATCHSection = Tab:NewSection("Left Hand")

AUTOCATCHSection:NewButton("Enable", "Made by yanros74", function()
game.Players.LocalPlayer.Character["Left Arm"].Massless = true
game.Players.LocalPlayer.Character["Left Arm"].Size = Vector3.new(30, 35, 1)
game.Players.LocalPlayer.Character["Left Arm"].Transparency = 0.9

end)

AUTOCATCHSection:NewButton("Disable", "Made by yanros74", function()
game.Players.LocalPlayer.Character["Left Arm"].Massless = true
game.Players.LocalPlayer.Character["Left Arm"].Size = Vector3.new(1, 2, 1)
game.Players.LocalPlayer.Character["Left Arm"].Transparency = 0

end)

--BALL TP

local Tab = Window:NewTab("Ball TP")
local Section = Tab:NewSection("pro script")


Section:NewButton("open gui", "Made by yanros74", function()
--pro script made by russv
-- prevent from being ran more than once


if not _G.ini then
_G.ini = true

local sound = Instance.new("Sound")
sound.SoundId = "rbxassetid://216917652"
sound.Parent = game:GetService("SoundService")
sound:Play()

teleport = false

wait()
game.StarterGui:SetCore("SendNotification", {
Title = "Ball tp script"; -- the title (ofc)
Text = "GUI Loaded - J to Hide/Show"; -- what the text says (ofc)
Duration = 5; -- how long the notification should in secounds
})

print "================BALL TP LOADED================"
print "================MADE BY russv#7269================"

local heartbeat = game:GetService("RunService").Heartbeat
spawn(function()
    while true do heartbeat:Wait()
            game.Players.LocalPlayer.MaximumSimulationRadius = math.pow(math.huge,math.huge)*math.huge
            sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",math.pow(math.huge,math.huge)*math.huge)
            game:GetService("RunService").Stepped:wait()
end
end)

local Imput = game:GetService("UserInputService")
local Plr = game.Players.LocalPlayer
local Mouse = Plr:GetMouse()

function To(position)
local Chr = Plr.Character
local sound2 = Instance.new("Sound")
sound2.SoundId = "rbxassetid://3398620867"
sound2.Parent = game:GetService("SoundService")
if Chr ~= nil then
if teleport == false then
for index, part in pairs(game:GetDescendants()) do
if part:IsA("BasePart" or "UnionOperation" or "Model") and part.Anchored == false and part:IsDescendantOf(game.Players.LocalPlayer.Character) == false and part.Name == "Torso" == false and part.Name == "Head" == false and part.Name == "Right Arm" == false and part.Name == "Left Arm" == false and part.Name == "Right Leg" == false and part.Name == "Left Leg" == false and part.Name == "HumanoidRootPart" == false then --// Checks Part Properties
    part.CFrame = CFrame.new(position) --TP Part To Mouse
    sound2:Play()

    if spam == true and part:FindFirstChild("BodyGyro") == nil then
    local bodyPos = Instance.new("BodyPosition")
    bodyPos.Position = part.Position
    bodyPos.MaxForce = Vector3.new(math.huge, math.huge, math.huge)
    bodyPos.P = 1e6
    bodyPos.Parent = part
    end
end
end
else

    Chr:MoveTo(position)
end
end
end





Imput.InputBegan:Connect(function(input)
   if input.UserInputType == Enum.UserInputType.MouseButton1 and Imput:IsKeyDown(Enum.KeyCode.LeftControl) then
       To(Mouse.Hit.p)
   end
end)







-- key that opens/closes the ui
local toggle_key = Enum.KeyCode.J

-- function that executes desired code
execute = function(name)



    for index, part in pairs(game:GetDescendants()) do
    if part:IsA("BasePart" or "UnionOperation" or "Model") and part.Anchored == false and part:IsDescendantOf(game.Players.LocalPlayer.Character) == false and part.Name == "Torso" == false and part.Name == "Head" == false and part.Name == "Right Arm" == false and part.Name == "Left Arm" == false and part.Name == "Right Leg" == false and part.Name == "Left Leg" == false and part.Name == "HumanoidRootPart" == false then --// Checks Part Properties
    part.CFrame = CFrame.new(game.workspace[name].Head.Position) --TP Part To User
    if spam == true and part:FindFirstChild("BodyGyro") == nil then
    local bodyPos = Instance.new("BodyPosition")
    bodyPos.Position = part.Position
    bodyPos.MaxForce = Vector3.new(math.huge, math.huge, math.huge)
    bodyPos.P = 1e6
    bodyPos.Parent = part
    end
    end
    end



end

local uis = game:GetService("UserInputService")
local ts = game:GetService("TweenService")

-- ui functions
fade = function(obj, len, props)
	ts:Create(obj, TweenInfo.new(len, Enum.EasingStyle.Sine), props):Play()
end

-- shorthand variables
local u2, c3 = UDim2.new, Color3.fromRGB
local u2f, c3w = u2(1, 0, 1, 0), c3(255, 255, 255)

-- ui init
local g = Instance.new("ScreenGui", game.CoreGui)
local f = Instance.new("Frame", g)
local t = Instance.new("TextLabel", f)
local c = Instance.new("ScrollingFrame", f)

-- core ui styling
local padding = Instance.new("UIPadding", f)
local maxsize = Instance.new("UISizeConstraint", f)
local textsize = Instance.new("UITextSizeConstraint", t)
local listcons = Instance.new("UIListLayout", c)

padding.PaddingBottom = UDim.new(0, 8)
padding.PaddingLeft = UDim.new(0, 15)
padding.PaddingRight = UDim.new(0, 15)
padding.PaddingTop = UDim.new(0, 0)

maxsize.MaxSize = Vector2.new(275, 450)
maxsize.MinSize = Vector2.new(200, 0)
textsize.MaxTextSize = 16
listcons.Padding = UDim.new(0, 3)

-- ui instance properties
g.Name = "unanchor_ui"
g.ResetOnSpawn = false
f.Name = "main"
t.Name = "header"

f.Size = u2(0.165, 0, 0.6, 0)
f.BorderSizePixel = 0
f.BackgroundTransparency = 0.3
f.Position = u2(1, -215, 0.5, -150)
f.BackgroundColor3 = c3()
f.AnchorPoint = Vector2.new(1, 0.5)
f.Position = u2(1, -15, 0.5, 0)

t.Size = u2(1, 0, 0.1, 0)
t.BackgroundTransparency = 1
t.TextColor3 = c3w
t.Font = Enum.Font.GothamBold
t.TextScaled = true
t.TextXAlignment = Enum.TextXAlignment.Center
t.Text = "Ball tp script"

c.Name = "playerlist"
c.Position = u2(0, 0, 0.1, 0)
c.Size = u2(1, 0, 0.45, 0)
c.BackgroundTransparency = 1
c.BorderSizePixel = 0
c.TopImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
c.BottomImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
c.ScrollingDirection = Enum.ScrollingDirection.Y
c.ScrollBarThickness = 5
c.VerticalScrollBarInset = Enum.ScrollBarInset.ScrollBar

-- playerlist entry ui template
local temp = Instance.new("Frame", f)
temp.Name = "temp"
temp.Visible = false
temp.Size = u2(1, -5, 0, 27)
temp.BackgroundTransparency = 0.5
temp.BorderSizePixel = 0
temp.ClipsDescendants = true
temp.BackgroundColor3 = c3()

local tpad = Instance.new("UIPadding", temp)
tpad.PaddingLeft = UDim.new(0, 5)
tpad.PaddingRight = UDim.new(0, 5)

local tb = Instance.new("TextButton", temp)
tb.Name = "button"
tb.BackgroundTransparency = 1
tb.ZIndex = 5
tb.BorderSizePixel = 0
tb.Text = ""
tb.Size = u2(1, 10, 1, 0)
tb.Position = u2(0, -5, 0, 0)

local tcl = Instance.new("TextLabel", temp)
tcl.Name = "username"
tcl.BackgroundTransparency = 1
tcl.BorderSizePixel = 0
tcl.Size = u2f
tcl.TextColor3 = c3w
tcl.TextXAlignment = Enum.TextXAlignment.Left
tcl.TextScaled = true
tcl.Size = u2(0.6, 0, 1, 0)
tcl.Font = Enum.Font.Gotham

local tcls = Instance.new("UITextSizeConstraint", tcl)
tcls.MaxTextSize = 14

local thumb = Instance.new("ImageLabel", temp)
thumb.Name = "thumb"
thumb.Size = u2(0.35, 0, 0.35, 0)
thumb.SizeConstraint = Enum.SizeConstraint.RelativeXX
thumb.Position = u2(1, 0, 0, -15)
thumb.AnchorPoint = Vector2.new(1, 0)
thumb.BackgroundTransparency = 1
thumb.BorderSizePixel = 0

-- settings ui
local sh = Instance.new("TextLabel", f)
sh.Name = "settings_header"
sh.Size = u2(1, 0, 0.1, 0)
sh.Position = u2(0, 0, 0.55, 0)
sh.BackgroundTransparency = 1
sh.BorderSizePixel = 0
sh.ZIndex = 3
sh.TextColor3 = c3w
sh.Font = Enum.Font.GothamBold
sh.TextScaled = true
sh.TextXAlignment = Enum.TextXAlignment.Center
sh.Text = "SETTINGS"

local shs = Instance.new("UITextSizeConstraint", sh)
shs.MaxTextSize = 16

local items = Instance.new("ScrollingFrame", f)
items.Name = "items"
items.Size = u2(1, 0, 0.35, 0)
items.Position = u2(0, 0, 0.65, 0)
items.BackgroundTransparency = 1
items.BorderSizePixel = 0
items.TopImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
items.BottomImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
items.ScrollingDirection = Enum.ScrollingDirection.Y
items.ScrollBarThickness = 5
items.VerticalScrollBarInset = Enum.ScrollBarInset.ScrollBar

local itemll = Instance.new("UIListLayout", items)
itemll.Padding = UDim.new(0, 3)

createSetting = function(name)
	local setting = Instance.new("Frame", items)
	setting.Size = u2(1, -5, 0, 27)
	setting.BackgroundColor3 = c3()
	setting.BackgroundTransparency = 0.5
	setting.BorderSizePixel = 0
	
	local spad = tpad:Clone()
	spad.Parent = setting
	
	local slab = tcl:Clone()
	slab.Name = "label"
	slab.Parent = setting
	slab.Size = u2(1, 0, 1, 0)
	slab.Text = name
	
	local stbt = tb:Clone()
	stbt.Parent = setting
	
	stbt.MouseEnter:connect(function()
		fade(setting, 0.25, {BackgroundTransparency = 0.8})
	end)
	
	stbt.MouseLeave:connect(function()
		fade(setting, 0.25, {BackgroundTransparency = 0.5})
	end)
	
	items.CanvasSize = u2(0, 0, 0, itemll.AbsoluteContentSize.Y)
	
	return stbt
end


-- settings & functionality



    local sound = Instance.new("Sound")
    sound.SoundId = "rbxassetid://179235828"
    sound.Parent = game:GetService("SoundService")

createSetting("Ball TP").MouseButton1Down:connect(function()
    for index, part in pairs(game:GetDescendants()) do
    if part:IsA("BasePart" or "UnionOperation" or "Model") and part.Anchored == false and part:IsDescendantOf(game.Players.LocalPlayer.Character) == false and part.Name == "Torso" == false and part.Name == "Head" == false and part.Name == "Right Arm" == false and part.Name == "Left Arm" == false and part.Name == "Right Leg" == false and part.Name == "Left Leg" == false and part.Name == "HumanoidRootPart" == false then --// Checks Part Properties
    sound:Play()
    if part:FindFirstChild("BodyForce") then
    part.BodyForce:Destroy()
    end

    if part:FindFirstChild("BodyGyro") then
    part.BodyGyro:Destroy()
    end

    if part:FindFirstChild("BodyPosition") then
    part.BodyPosition:Destroy()
    end

    if part:FindFirstChild("BodyThrust") then
    part.BodyThrust:Destroy()
    end
end
end
end)





createEntry = function(name, id)
	local entry = temp:Clone()
	entry.Parent = c
	entry.username.Text = name
	entry.thumb.Image = game:GetService("Players"):GetUserThumbnailAsync(id, Enum.ThumbnailType.HeadShot, Enum.ThumbnailSize.Size100x100)
	entry.Visible = true
	entry.LayoutOrder = #c:GetChildren()
	entry.Name = name

    local sound = Instance.new("Sound")
    sound.SoundId = "rbxassetid://3398620867"
    sound.Parent = game:GetService("SoundService")
	-- handle clicking for player
	entry.button.MouseButton1Down:connect(function()
		execute(name)
        sound:Play()
	end)
	
	entry.button.MouseEnter:connect(function()
		fade(entry, 0.25, {BackgroundTransparency = 0.8})
	end)
	
	entry.button.MouseLeave:connect(function()
		fade(entry, 0.25, {BackgroundTransparency = 0.5})
	end)
end

deleteEntry = function(name)
	for _,v in pairs(c:GetChildren()) do
		if v.Name == name then
			v:Destroy()
		end
	end
end

-- create entry for client
createEntry(game.Players.LocalPlayer.Name, game.Players.LocalPlayer.UserId)

-- create entries for all other players
for _,v in pairs(game.Players:GetPlayers()) do
	if v ~= game.Players.LocalPlayer then
		createEntry(v.Name, v.UserId)
	end
end

listcons:GetPropertyChangedSignal("AbsoluteContentSize"):connect(function()
	c.CanvasSize = u2(0, 0, 0, listcons.AbsoluteContentSize.Y)
end)

itemll:GetPropertyChangedSignal("AbsoluteContentSize"):connect(function()
	items.CanvasSize = u2(0, 0, 0, itemll.AbsoluteContentSize.Y)
end)

uis.InputBegan:connect(function(input, gpe)
	if not gpe then
		if input.KeyCode == toggle_key then
			g.Enabled = not g.Enabled
		end
	end
end)

-- dragging code, ripped from https://devforum.roblox.com/t/draggable-property-is-hidden-on-gui-objects/107689/5
local dragging
local dragInput
local dragStart
local startPos

local function update(input)
	local delta = input.Position - dragStart
	f.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
end

f.InputBegan:Connect(function(input)
	if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
		dragging = true
		dragStart = input.Position
		startPos = f.Position
		
		input.Changed:Connect(function()
			if input.UserInputState == Enum.UserInputState.End then
				dragging = false
			end
		end)
	end
end)

f.InputChanged:Connect(function(input)
	if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
		dragInput = input
	end
end)

uis.InputChanged:Connect(function(input)
	if input == dragInput and dragging then
		update(input)
	end
end)

game.Players.PlayerAdded:connect(function(plr)
	createEntry(plr.Name, plr.UserId)
end)

game.Players.PlayerRemoving:connect(function(plr)
	deleteEntry(plr.Name)
end)
else
print "================ALREADY LOADED================"



    local sound = Instance.new("Sound")
    sound.SoundId = "rbxassetid://2130284653"
    sound.Parent = game:GetService("SoundService")
sound:Play()

game.StarterGui:SetCore("SendNotification", {
Title = "pro"; -- the title (ofc)
Text = "u cant because u noob"; -- what the text says (ofc)
Duration = 5; -- how long the notification should in secounds
})
end
end)

--TP TO GK LINES (FOR RMFL LEAGUE IT WILL NOT WORK ON ANOTHER PITCHS)

local Tab = Window:NewTab("tElEpOrT")
local Section = Tab:NewSection("RMFL Away GK")

Section:NewButton("Teleport", "Made by yanros74", function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-0, 6, 325)
end)

local Section = Tab:NewSection("RMFL Home GK")

Section:NewButton("Teleport", "Made by yanros74", function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(2, 6, -323)
end)

local Section = Tab:NewSection("RMFL Middle")

Section:NewButton("Teleport", "Made by yanros74", function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-0, 6, 2)
end)

local Section = Tab:NewSection("SFSL Away GK2")

Section:NewButton("Teleport", "Made by yanros74", function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1, 503, 325)
end)

local Section = Tab:NewSection("SFSL Home GK2")

Section:NewButton("Teleport", "Made by yanros74", function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-0, 503, -325)
end)

local Section = Tab:NewSection("SFSL Middle2")

Section:NewButton("Teleport", "Made by yanros74", function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-0, 503, 0)
end)

--FPS BOOSTER

local Tab = Window:NewTab("Fps Booster")
local Section = Tab:NewSection("you need fpsunlocker")


Section:NewButton("Execute", "Made by yanros74", function()
local decalsyeeted = true -- Leaving this on makes games look shitty but the fps goes up by at least 20.
local g = game
local w = g.Workspace
local l = g.Lighting
local t = w.Terrain
sethiddenproperty(l,"Technology",2)
sethiddenproperty(t,"Decoration",false)
t.WaterWaveSize = 0
t.WaterWaveSpeed = 0
t.WaterReflectance = 0
t.WaterTransparency = 0
l.GlobalShadows = 0
l.FogEnd = 9e9
l.Brightness = 0
settings().Rendering.QualityLevel = "Level01"
for i, v in pairs(w:GetDescendants()) do
    if v:IsA("BasePart") and not v:IsA("MeshPart") then
        v.Material = "Plastic"
        v.Reflectance = 0
    elseif (v:IsA("Decal") or v:IsA("Texture")) and decalsyeeted then
        v.Transparency = 1
    elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
        v.Lifetime = NumberRange.new(0)
    elseif v:IsA("Explosion") then
        v.BlastPressure = 1
        v.BlastRadius = 1
    end
end
for i = 1,#l:GetChildren() do
    e=l:GetChildren()[i]
    if e:IsA("BlurEffect") or e:IsA("SunRaysEffect") or e:IsA("ColorCorrectionEffect") or e:IsA("BloomEffect") or e:IsA("DepthOfFieldEffect") then
        e.Enabled = false
    end
end
end)

local Section = Tab:NewSection("delete smt in pitch")


Section:NewButton("click two times", "Made by yanros74", function()
game:GetService("Workspace").idk:Destroy() 
end)

local Section = Tab:NewSection("delete door")


Section:NewButton("unlock door", "Made by yanros74", function()
game:GetService("Workspace").Pitch.Walls.Door:Destroy() 
end)

--FAKE AFK

local Tab = Window:NewTab("fake afk for sfsl")
local Section = Tab:NewSection("it works")


Section:NewButton("Enable", "Made by yanros74", function()
local args = {
    [1] = true
}

game:GetService("ReplicatedStorage").IsAFK:FireServer(unpack(args))

end)

local Tab = Window:NewTab("little trollin'")
local Section = Tab:NewSection("Trolling")

Section:NewButton("Amogus", "Made by yanros74", function()
--FOR MPSHUB
 
local lp = game:FindService("Players").LocalPlayer
 
local function gplr(String)
	local Found = {}
	local strl = String:lower()
	if strl == "all" then
		for i,v in pairs(game:FindService("Players"):GetPlayers()) do
			table.insert(Found,v)
		end
	elseif strl == "others" then
		for i,v in pairs(game:FindService("Players"):GetPlayers()) do
			if v.Name ~= lp.Name then
				table.insert(Found,v)
			end
		end 
	elseif strl == "me" then
		for i,v in pairs(game:FindService("Players"):GetPlayers()) do
			if v.Name == lp.Name then
				table.insert(Found,v)
			end
		end 
	else
		for i,v in pairs(game:FindService("Players"):GetPlayers()) do
			if v.Name:lower():sub(1, #String) == String:lower() then
				table.insert(Found,v)
			end
		end 
	end
	return Found 
end
 
local function notif(str,dur)
	game:FindService("StarterGui"):SetCore("SendNotification", {
		Title = ":skull:",
		Text = str,
		Icon = "rbxassetid://2005276185",
		Duration = dur or 3
	})
end
 
--// sds
 
local h = Instance.new("ScreenGui")
local Main = Instance.new("ImageLabel")
local Top = Instance.new("Frame")
local Title = Instance.new("TextLabel")
local TextBox = Instance.new("TextBox")
local TextButton = Instance.new("TextButton")
 
h.Name = "h"
h.Parent = game:GetService("CoreGui")
h.ResetOnSpawn = false
 
Main.Name = "Main"
Main.Parent = h
Main.Active = true
Main.Draggable = true
Main.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Main.BorderSizePixel = 0
Main.Position = UDim2.new(0.174545452, 0, 0.459574461, 0)
Main.Size = UDim2.new(0, 454, 0, 218)
Main.Image = "rbxassetid://2005276185"
 
Top.Name = "Top"
Top.Parent = Main
Top.BackgroundColor3 = Color3.fromRGB(57, 57, 57)
Top.BorderSizePixel = 0
Top.Size = UDim2.new(0, 454, 0, 44)
 
Title.Name = "Title"
Title.Parent = Top
Title.BackgroundColor3 = Color3.fromRGB(49, 49, 49)
Title.BorderSizePixel = 0
Title.Position = UDim2.new(0, 0, 0.295454562, 0)
Title.Size = UDim2.new(0, 454, 0, 30)
Title.Font = Enum.Font.SourceSans
Title.Text = "FOR MPSHUB"
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.TextScaled = true
Title.TextSize = 14.000
Title.TextWrapped = true
 
TextBox.Parent = Main
TextBox.BackgroundColor3 = Color3.fromRGB(49, 49, 49)
TextBox.BorderSizePixel = 0
TextBox.Position = UDim2.new(0.0704845786, 0, 0.270642221, 0)
TextBox.Size = UDim2.new(0, 388, 0, 62)
TextBox.Font = Enum.Font.SourceSans
TextBox.PlaceholderText = "Who do i fling(write his name)"
TextBox.Text = ""
TextBox.TextColor3 = Color3.fromRGB(255, 255, 255)
TextBox.TextScaled = true
TextBox.TextSize = 14.000
TextBox.TextWrapped = true
 
TextButton.Parent = Main
TextButton.BackgroundColor3 = Color3.fromRGB(49, 49, 49)
TextButton.BorderSizePixel = 0
TextButton.Position = UDim2.new(0.10352423, 0, 0.596330225, 0)
TextButton.Size = UDim2.new(0, 359, 0, 50)
TextButton.Font = Enum.Font.SourceSans
TextButton.Text = "Fling him"
TextButton.TextColor3 = Color3.fromRGB(255, 255, 255)
TextButton.TextScaled = true
TextButton.TextSize = 14.000
TextButton.TextWrapped = true
 
TextButton.MouseButton1Click:Connect(function()
	local Target = gplr(TextBox.Text)
	if Target[1] then
		Target = Target[1]
 
		local Thrust = Instance.new('BodyThrust', lp.Character.HumanoidRootPart)
		Thrust.Force = Vector3.new(9999,9999,9999)
		Thrust.Name = "YeetForce"
		repeat
			lp.Character.HumanoidRootPart.CFrame = Target.Character.HumanoidRootPart.CFrame
			Thrust.Location = Target.Character.HumanoidRootPart.Position
			game:FindService("RunService").Heartbeat:wait()
		until not Target.Character:FindFirstChild("Head")
	else
		notif("Invalid player")
	end
end)
 
--//fsddfsdf
notif("Loaded successfully! Created by russv#7269", 5)
end)

local Section = Tab:NewSection("BestSCRIPTS")
Section:NewButton("Astra", "Made by yanros74", function()
--//====================================================\\--
--||               CREATED BY RUSSV
--\\====================================================//--
 
 
 
wait(0.2)
 
 
 
Player = game:GetService("Players").LocalPlayer
PlayerGui = Player.PlayerGui
Cam = workspace.CurrentCamera
Backpack = Player.Backpack
Character = Player.Character
Humanoid = Character.Humanoid
Mouse = Player:GetMouse()
RootPart = Character["HumanoidRootPart"]
Torso = Character["Torso"]
Head = Character["Head"]
RightArm = Character["Right Arm"]
LeftArm = Character["Left Arm"]
RightLeg = Character["Right Leg"]
LeftLeg = Character["Left Leg"]
RootJoint = RootPart["RootJoint"]
Neck = Torso["Neck"]
RightShoulder = Torso["Right Shoulder"]
LeftShoulder = Torso["Left Shoulder"]
RightHip = Torso["Right Hip"]
LeftHip = Torso["Left Hip"]
local sick = Instance.new("Sound",Character)
sick.SoundId = "rbxassetid://195900687"
sick.Looped = true
sick.Pitch = 1
sick.Volume = 3
sick:Play()
 
IT = Instance.new
CF = CFrame.new
VT = Vector3.new
RAD = math.rad
C3 = Color3.new
UD2 = UDim2.new
BRICKC = BrickColor.new
ANGLES = CFrame.Angles
EULER = CFrame.fromEulerAnglesXYZ
COS = math.cos
ACOS = math.acos
SIN = math.sin
ASIN = math.asin
ABS = math.abs
MRANDOM = math.random
FLOOR = math.floor
 
function CreateMesh(MESH, PARENT, MESHTYPE, MESHID, TEXTUREID, SCALE, OFFSET)
    local NEWMESH = IT(MESH)
    if MESH == "SpecialMesh" then
        NEWMESH.MeshType = MESHTYPE
        if MESHID ~= "nil" and MESHID ~= "" then
            NEWMESH.MeshId = "http://www.roblox.com/asset/?id="..MESHID
        end
        if TEXTUREID ~= "nil" and TEXTUREID ~= "" then
            NEWMESH.TextureId = "http://www.roblox.com/asset/?id="..TEXTUREID
        end
    end
    NEWMESH.Offset = OFFSET or VT(0, 0, 0)
    NEWMESH.Scale = SCALE
    NEWMESH.Parent = PARENT
    return NEWMESH
end
 
function CreatePart(FORMFACTOR, PARENT, MATERIAL, REFLECTANCE, TRANSPARENCY, BRICKCOLOR, NAME, SIZE, ANCHOR)
    local NEWPART = IT("Part")
    NEWPART.formFactor = FORMFACTOR
    NEWPART.Reflectance = REFLECTANCE
    NEWPART.Transparency = TRANSPARENCY
    NEWPART.CanCollide = false
    NEWPART.Locked = true
    NEWPART.Anchored = true
    if ANCHOR == false then
        NEWPART.Anchored = false
    end
    NEWPART.BrickColor = BRICKC(tostring(BRICKCOLOR))
    NEWPART.Name = NAME
    NEWPART.Size = SIZE
    NEWPART.Position = Torso.Position
    NEWPART.Material = MATERIAL
    NEWPART:BreakJoints()
    NEWPART.Parent = PARENT
    return NEWPART
end
 
--//=================================\\
--||          CUSTOMIZATION
--\\=================================//
 
Player_Size = 1 --Size of the player.
Animation_Speed = 3
Frame_Speed = 1 / 60 -- (1 / 30) OR (1 / 60)
 
local Speed = 16
local Effects2 = {}
 
--//=================================\\
--||      END OF CUSTOMIZATION
--\\=================================//
 
    local function weldBetween(a, b)
        local weldd = Instance.new("ManualWeld")
        weldd.Part0 = a
        weldd.Part1 = b
        weldd.C0 = CFrame.new()
        weldd.C1 = b.CFrame:inverse() * a.CFrame
        weldd.Parent = a
        return weldd
    end
 
--//=================================\\
--||          USEFUL VALUES
--\\=================================//
 
local ROOTC0 = CF(0, 0, 0) * ANGLES(RAD(-90), RAD(0), RAD(180))
local NECKC0 = CF(0, 1, 0) * ANGLES(RAD(-90), RAD(0), RAD(180))
local RIGHTSHOULDERC0 = CF(-0.5, 0, 0) * ANGLES(RAD(0), RAD(90), RAD(0))
local LEFTSHOULDERC0 = CF(0.5, 0, 0) * ANGLES(RAD(0), RAD(-90), RAD(0))
local CHANGEDEFENSE = 0
local CHANGEDAMAGE = 0
local CHANGEMOVEMENT = 0
local ANIM = "Idle"
local ATTACK = false
local EQUIPPED = false
local HOLD = false
local COMBO = 1
local Rooted = false
local SINE = 0
local KEYHOLD = false
local CHANGE = 2 / Animation_Speed
local WALKINGANIM = false
local WALK = 0
local VALUE1 = false
local VALUE2 = false
local ROBLOXIDLEANIMATION = IT("Animation")
ROBLOXIDLEANIMATION.Name = "Roblox Idle Animation"
ROBLOXIDLEANIMATION.AnimationId = "http://www.roblox.com/asset/?id=180435571"
--ROBLOXIDLEANIMATION.Parent = Humanoid
local WEAPONGUI = IT("ScreenGui", PlayerGui)
WEAPONGUI.Name = "Weapon GUI"
local Effects = IT("Folder", Character)
Effects.Name = "Effects"
local ANIMATOR = Humanoid.Animator
local ANIMATE = Character.Animate
local HITPLAYERSOUNDS = {--[["199149137", "199149186", "199149221", "199149235", "199149269", "199149297"--]]"263032172", "263032182", "263032200", "263032221", "263032252", "263033191"}
local HITARMORSOUNDS = {"199149321", "199149338", "199149367", "199149409", "199149452"}
local HITWEAPONSOUNDS = {"199148971", "199149025", "199149072", "199149109", "199149119"}
local HITBLOCKSOUNDS = {"199148933", "199148947"}
local UNANCHOR = true
 
local SKILLTEXTCOLOR = C3(0.05,0.05,0.15)
 
--//=================================\\
--\\=================================//
 
 
--//=================================\\
--|| SAZERENOS' ARTIFICIAL HEARTBEAT
--\\=================================//
 
ArtificialHB = Instance.new("BindableEvent", script)
ArtificialHB.Name = "ArtificialHB"
 
script:WaitForChild("ArtificialHB")
 
frame = Frame_Speed
tf = 0
allowframeloss = false
tossremainder = false
lastframe = tick()
script.ArtificialHB:Fire()
 
game:GetService("RunService").Heartbeat:connect(function(s, p)
    tf = tf + s
    if tf >= frame then
        if allowframeloss then
            script.ArtificialHB:Fire()
            lastframe = tick()
        else
            for i = 1, math.floor(tf / frame) do
                script.ArtificialHB:Fire()
            end
        lastframe = tick()
        end
        if tossremainder then
            tf = 0
        else
            tf = tf - frame * math.floor(tf / frame)
        end
    end
end)
 
--//=================================\\
--\\=================================//
 
 
 
 
 
--//=================================\\
--||          SOME FUNCTIONS
--\\=================================//
 
function Raycast(POSITION, DIRECTION, RANGE, IGNOREDECENDANTS)
    return workspace:FindPartOnRay(Ray.new(POSITION, DIRECTION.unit * RANGE), IGNOREDECENDANTS)
end
 
function PositiveAngle(NUMBER)
    if NUMBER >= 0 then
        NUMBER = 0
    end
    return NUMBER
end
 
function NegativeAngle(NUMBER)
    if NUMBER <= 0 then
        NUMBER = 0
    end
    return NUMBER
end
 
function Swait(NUMBER)
    if NUMBER == 0 or NUMBER == nil then
        ArtificialHB.Event:wait()
    else
        for i = 1, NUMBER do
            ArtificialHB.Event:wait()
        end
    end
end
 
function QuaternionFromCFrame(cf)
    local mx, my, mz, m00, m01, m02, m10, m11, m12, m20, m21, m22 = cf:components()
    local trace = m00 + m11 + m22
    if trace > 0 then
        local s = math.sqrt(1 + trace)
        local recip = 0.5 / s
        return (m21 - m12) * recip, (m02 - m20) * recip, (m10 - m01) * recip, s * 0.5
    else
        local i = 0
        if m11 > m00 then
            i = 1
        end
        if m22 > (i == 0 and m00 or m11) then
            i = 2
        end
        if i == 0 then
            local s = math.sqrt(m00 - m11 - m22 + 1)
            local recip = 0.5 / s
            return 0.5 * s, (m10 + m01) * recip, (m20 + m02) * recip, (m21 - m12) * recip
        elseif i == 1 then
            local s = math.sqrt(m11 - m22 - m00 + 1)
            local recip = 0.5 / s
            return (m01 + m10) * recip, 0.5 * s, (m21 + m12) * recip, (m02 - m20) * recip
        elseif i == 2 then
            local s = math.sqrt(m22 - m00 - m11 + 1)
            local recip = 0.5 / s return (m02 + m20) * recip, (m12 + m21) * recip, 0.5 * s, (m10 - m01) * recip
        end
    end
end
 
function QuaternionToCFrame(px, py, pz, x, y, z, w)
    local xs, ys, zs = x + x, y + y, z + z
    local wx, wy, wz = w * xs, w * ys, w * zs
    local xx = x * xs
    local xy = x * ys
    local xz = x * zs
    local yy = y * ys
    local yz = y * zs
    local zz = z * zs
    return CFrame.new(px, py, pz, 1 - (yy + zz), xy - wz, xz + wy, xy + wz, 1 - (xx + zz), yz - wx, xz - wy, yz + wx, 1 - (xx + yy))
end
 
function QuaternionSlerp(a, b, t)
    local cosTheta = a[1] * b[1] + a[2] * b[2] + a[3] * b[3] + a[4] * b[4]
    local startInterp, finishInterp;
    if cosTheta >= 0.0001 then
        if (1 - cosTheta) > 0.0001 then
            local theta = ACOS(cosTheta)
            local invSinTheta = 1 / SIN(theta)
            startInterp = SIN((1 - t) * theta) * invSinTheta
            finishInterp = SIN(t * theta) * invSinTheta
        else
            startInterp = 1 - t
            finishInterp = t
        end
    else
        if (1 + cosTheta) > 0.0001 then
            local theta = ACOS(-cosTheta)
            local invSinTheta = 1 / SIN(theta)
            startInterp = SIN((t - 1) * theta) * invSinTheta
            finishInterp = SIN(t * theta) * invSinTheta
        else
            startInterp = t - 1
            finishInterp = t
        end
    end
    return a[1] * startInterp + b[1] * finishInterp, a[2] * startInterp + b[2] * finishInterp, a[3] * startInterp + b[3] * finishInterp, a[4] * startInterp + b[4] * finishInterp
end
 
function Clerp(a, b, t)
    local qa = {QuaternionFromCFrame(a)}
    local qb = {QuaternionFromCFrame(b)}
    local ax, ay, az = a.x, a.y, a.z
    local bx, by, bz = b.x, b.y, b.z
    local _t = 1 - t
    return QuaternionToCFrame(_t * ax + t * bx, _t * ay + t * by, _t * az + t * bz, QuaternionSlerp(qa, qb, t))
end
 
function CreateFrame(PARENT, TRANSPARENCY, BORDERSIZEPIXEL, POSITION, SIZE, COLOR, BORDERCOLOR, NAME)
    local frame = IT("Frame")
    frame.BackgroundTransparency = TRANSPARENCY
    frame.BorderSizePixel = BORDERSIZEPIXEL
    frame.Position = POSITION
    frame.Size = SIZE
    frame.BackgroundColor3 = COLOR
    frame.BorderColor3 = BORDERCOLOR
    frame.Name = NAME
    frame.Parent = PARENT
    return frame
end
 
function CreateLabel(PARENT, TEXT, TEXTCOLOR, TEXTFONTSIZE, TEXTFONT, TRANSPARENCY, BORDERSIZEPIXEL, STROKETRANSPARENCY, NAME)
    local label = IT("TextLabel")
    label.BackgroundTransparency = 1
    label.Size = UD2(1, 0, 1, 0)
    label.Position = UD2(0, 0, 0, 0)
    label.TextColor3 = TEXTCOLOR
    label.TextStrokeTransparency = STROKETRANSPARENCY
    label.TextTransparency = TRANSPARENCY
    label.FontSize = TEXTFONTSIZE
    label.Font = TEXTFONT
    label.BorderSizePixel = BORDERSIZEPIXEL
    label.TextScaled = false
    label.Text = TEXT
    label.Name = NAME
    label.Parent = PARENT
    return label
end
 
function NoOutlines(PART)
    PART.TopSurface, PART.BottomSurface, PART.LeftSurface, PART.RightSurface, PART.FrontSurface, PART.BackSurface = 10, 10, 10, 10, 10, 10
end
 
 
function CreateWeldOrSnapOrMotor(TYPE, PARENT, PART0, PART1, C0, C1)
    local NEWWELD = IT(TYPE)
    NEWWELD.Part0 = PART0
    NEWWELD.Part1 = PART1
    NEWWELD.C0 = C0
    NEWWELD.C1 = C1
    NEWWELD.Parent = PARENT
    return NEWWELD
end
 
function CreateSound(ID, PARENT, VOLUME, PITCH)
    local NEWSOUND = nil
    coroutine.resume(coroutine.create(function()
        NEWSOUND = IT("Sound", PARENT)
        NEWSOUND.Volume = VOLUME
        NEWSOUND.Pitch = PITCH
        NEWSOUND.SoundId = "http://www.roblox.com/asset/?id="..ID
        Swait()
        NEWSOUND:play()
        game:GetService("Debris"):AddItem(NEWSOUND, 10)
    end))
    return NEWSOUND
end
 
function CFrameFromTopBack(at, top, back)
    local right = top:Cross(back)
    return CF(at.x, at.y, at.z, right.x, top.x, back.x, right.y, top.y, back.y, right.z, top.z, back.z)
end
 
function CreateSwirl(SIZE,WAIT,CFRAME,DOESROT,ROT,COLOR,GROW)
    local wave = CreatePart(3, Effects, "Neon", 0, 0.5, BRICKC(COLOR), "Effect", VT(0,0,0))
    wave.Color = COLOR
    local mesh = CreateMesh("SpecialMesh", wave, "FileMesh", "1051557", "", SIZE, VT(0,0,0))
    wave.CFrame = CFRAME
    coroutine.resume(coroutine.create(function(PART)
        for i = 1, WAIT do
            Swait()
            mesh.Scale = mesh.Scale + GROW
            mesh.Offset = VT(0,0,-(mesh.Scale.X/8))
            if DOESROT == true then
                wave.CFrame = wave.CFrame * CFrame.fromEulerAnglesXYZ(0,ROT,0)
            end
            wave.Transparency = wave.Transparency + (0.5/WAIT)
            if wave.Transparency > 0.99 then
                wave:remove()
            end
        end
    end))
end

function MagicSphere(SIZE,WAIT,CFRAME,COLOR,GROW)
    local wave = CreatePart(3, Effects, "Neon", 0, 0, BRICKC(COLOR), "Effect", VT(1,1,1), true)
    wave.Color = COLOR
    local mesh = CreateMesh("SpecialMesh", wave, "Sphere", "", "", SIZE, VT(0,0,0))
    wave.CFrame = CFRAME
    coroutine.resume(coroutine.create(function(PART)
        for i = 1, WAIT do
            Swait()
            mesh.Scale = mesh.Scale + GROW
            wave.Transparency = wave.Transparency + (1/WAIT)
            if wave.Transparency > 0.99 then
                wave:remove()
            end
        end
    end))
end
 
function Slice(KIND,SIZE,WAIT,CFRAME,COLOR,GROW)
    local wave = CreatePart(3, Effects, "Neon", 0, 0.5, BRICKC(COLOR), "Effect", VT(1,1,1), true)
    local mesh = nil
    if KIND == "Base" then
        mesh = CreateMesh("SpecialMesh", wave, "FileMesh", "448386996", "", VT(0,SIZE/10,SIZE/10), VT(0,0,0))
    elseif KIND == "Thin" then
        mesh = CreateMesh("SpecialMesh", wave, "FileMesh", "662586858", "", VT(SIZE/10,0,SIZE/10), VT(0,0,0))
    elseif KIND == "Round" then
        mesh = CreateMesh("SpecialMesh", wave, "FileMesh", "662585058", "", VT(SIZE/10,0,SIZE/10), VT(0,0,0))
    end
    wave.CFrame = CFRAME
    coroutine.resume(coroutine.create(function(PART)
        for i = 1, WAIT do
            Swait()
            mesh.Scale = mesh.Scale + GROW/10
            wave.Transparency = wave.Transparency + (0.5/WAIT)
            if wave.Transparency > 0.99 then
                wave:remove()
            end
        end
    end))
end
 
function MakeForm(PART,TYPE)
    if TYPE == "Cyl" then
        local MSH = IT("CylinderMesh",PART)
    elseif TYPE == "Ball" then
        local MSH = IT("SpecialMesh",PART)
        MSH.MeshType = "Sphere"
    elseif TYPE == "Wedge" then
        local MSH = IT("SpecialMesh",PART)
        MSH.MeshType = "Wedge"
    end
end
 
function CheckTableForString(Table, String)
    for i, v in pairs(Table) do
        if string.find(string.lower(String), string.lower(v)) then
            return true
        end
    end
    return false
end
 
function CheckIntangible(Hit)
    local ProjectileNames = {"Water", "Arrow", "Projectile", "Effect", "Rail", "Lightning", "Bullet"}
    if Hit and Hit.Parent then
        if ((not Hit.CanCollide or CheckTableForString(ProjectileNames, Hit.Name)) and not Hit.Parent:FindFirstChild("Humanoid")) then
            return true
        end
    end
    return false
end
 
Debris = game:GetService("Debris")
 
function CastZapRay(StartPos, Vec, Length, Ignore, DelayIfHit)
    local Direction = CFrame.new(StartPos, Vec).lookVector
    local Ignore = ((type(Ignore) == "table" and Ignore) or {Ignore})
    local RayHit, RayPos, RayNormal = game:GetService("Workspace"):FindPartOnRayWithIgnoreList(Ray.new(StartPos, Direction * Length), Ignore)
    if RayHit and CheckIntangible(RayHit) then
        if DelayIfHit then
            wait()
        end
        RayHit, RayPos, RayNormal = CastZapRay((RayPos + (Vec * 0.01)), Vec, (Length - ((StartPos - RayPos).magnitude)), Ignore, DelayIfHit)
    end
    return RayHit, RayPos, RayNormal
end
 
function FireArc(Part,ToLocation,AmountOfTime,Height,DoesCourontine)
    if DoesCourontine == false then
        local Direction = CF(Part.Position,ToLocation)
        local Distance = (Part.Position - ToLocation).magnitude
        for i = 1, AmountOfTime do
            Swait()
            Part.CFrame = Direction*CF(0,(AmountOfTime/200)+((AmountOfTime/Height)-((i*2)/Height)),-Distance/AmountOfTime)
            Direction = Part.CFrame
        end
        Part:remove()
    elseif DoesCourontine == true then
        coroutine.resume(coroutine.create(function()
            local Direction = CF(Part.Position,ToLocation)
            local Distance = (Part.Position - ToLocation).magnitude
            for i = 1, AmountOfTime do
                Swait()
                Part.CFrame = Direction*CF(0,(AmountOfTime/200)+((AmountOfTime/Height)-((i*2)/Height)),-Distance/AmountOfTime)
                Direction = Part.CFrame
            end
            Part:remove()
        end))
    end
end
 
function turnto(position)
    RootPart.CFrame=CFrame.new(RootPart.CFrame.p,VT(position.X,RootPart.Position.Y,position.Z)) * CFrame.new(0, 0, 0)
end
 
--//=================================\\
--||         WEAPON CREATION
--\\=================================//
 
local naeeym2 = Instance.new("BillboardGui",Character)
naeeym2.AlwaysOnTop = true
naeeym2.Size = UDim2.new(5,35,2,15)
naeeym2.StudsOffset = Vector3.new(0,3,0)
naeeym2.Adornee = Character.Head
naeeym2.Name = "Name"
naeeym2.PlayerToHideFrom = Player
local tecks2 = Instance.new("TextLabel",naeeym2)
tecks2.BackgroundTransparency = 1
tecks2.TextScaled = true
tecks2.BorderSizePixel = 0
tecks2.Text = "Dominus Astra"
tecks2.Font = "Fantasy"
tecks2.TextSize = 30
tecks2.TextStrokeTransparency = 0
tecks2.TextColor3 = Color3.new(0.05,0.05,0.15)
tecks2.TextStrokeColor3 = Color3.new(0,0,0)
tecks2.Size = UDim2.new(1,0,0.5,0)
tecks2.Parent = naeeym2
 
function Transparency(TRANS)
    tecks2.TextTransparency = TRANS
    tecks2.TextStrokeTransparency = TRANS
    for _, c in pairs(Character:GetChildren()) do
        if c.ClassName == "Part" and c ~= RootPart then
            c.Transparency = TRANS
            if c:FindFirstChildOfClass("Decal") then
                c:FindFirstChildOfClass("Decal").Transparency = TRANS
            end
        elseif c.ClassName == "Accessory" then
            c.Handle.Transparency = TRANS
        elseif c.ClassName == "Model" then
            for _, q in pairs(c:GetChildren()) do
                if q.ClassName == "Part" then
                    q.Transparency = TRANS
                    if q:FindFirstChildOfClass("Decal") then
                        q:FindFirstChildOfClass("Decal").Transparency = TRANS
                    end
                end
            end
        end
    end
end
 
Humanoid.Died:connect(function()
    Humanoid.Parent = nil
    Humanoid.MaxHealth = "inf"
    Humanoid.Health = "inf"
    refit()
    Humanoid.Parent = Character
    CreateSound("907330011", Head, 10, 1.2)
end)
 
local SKILL1FRAME = CreateFrame(WEAPONGUI, 1, 2, UD2(0.23, 0, 0.80, 0), UD2(0.26, 0, 0.07, 0), C3(0,0,0), C3(0, 0, 0), "Skill 1 Frame")
local SKILL2FRAME = CreateFrame(WEAPONGUI, 1, 2, UD2(0.50, 0, 0.80, 0), UD2(0.26, 0, 0.07, 0), C3(0,0,0), C3(0, 0, 0), "Skill 2 Frame")
local SKILL3FRAME = CreateFrame(WEAPONGUI, 1, 2, UD2(0.365, 0, 0.1, 0), UD2(0.26, 0, 0.07, 0), C3(0,0,0), C3(0, 0, 0), "Skill 3 Frame")
local SKILLEFRAME = CreateFrame(WEAPONGUI, 1, 2, UD2(0.365, 0, 0.9, 0), UD2(0.26, 0, 0.07, 0), C3(0,0,0), C3(0, 0, 0), "Skill Warp Frame")
 
local SKILL1TEXT = CreateLabel(SKILL1FRAME, "[Z] Lunar Blast", SKILLTEXTCOLOR, 7, "Fantasy", 0, 2, 0, "Text 1")
local SKILL2TEXT = CreateLabel(SKILL2FRAME, "[B] Star Cutter", SKILLTEXTCOLOR, 7, "Fantasy", 0, 2, 0, "Text 2")
local SKILL3TEXT = CreateLabel(SKILL3FRAME, "[C] Supernova", SKILLTEXTCOLOR, 10, "Fantasy", 0, 2, 0, "Text 3")
local SKILLETEXT = CreateLabel(SKILLEFRAME, "[Q] Astral Hop", SKILLTEXTCOLOR, 7, "Fantasy", 0, 2, 0, "Text Warp")
 
--//=================================\\
--||            DAMAGING
--\\=================================//
 
function killnearest(position,range,maxstrength)
    for i,v in ipairs(workspace:GetChildren()) do
    local body = v:GetChildren()
        for part = 1, #body do
            if((body[part].ClassName == "Part" or body[part].ClassName == "MeshPart") and v ~= Character) then
                if(body[part].Position - position).Magnitude < range then
                    if v.ClassName == "Model" then
                        v:BreakJoints()
                    end
                    --table.insert(Effects2,{body[part],"Disappear",0.02,2,2,2,2})
                    local bv = Instance.new("BodyVelocity")
                    bv.maxForce = Vector3.new(1e9, 1e9, 1e9)
                    bv.velocity = CF(position,body[part].Position).lookVector*maxstrength
                    bv.Parent = body[part]
                    Debris:AddItem(bv,0.2)
                end
            end
        end
        if v.ClassName == "Part" then
            if v.Anchored == false and (v.Position - position).Magnitude < range then
                --table.insert(Effects2,{v,"Disappear",0.02,2,2,2,2})
                v.Velocity = CFrame.new(position,v.Position).lookVector*5*maxstrength
            end
        end
    end
end
 
--//=================================\\
--||    ATTACK FUNCTIONS AND STUFF
--\\=================================//
 
function Lunar_Blast()
    local HITBODIES = {}
    local CENTER = CreatePart(3, Effects, "SmoothPlastic", 0, 1, "Relly red", "CenterPart", VT(0,0,0))
    local HITFLOOR,ECH,NORMAL = Raycast(Mouse.Hit.p+VT(0,2,0), (CF(Mouse.Hit.p, Mouse.Hit.p + VT(0, -1, 0))).lookVector, 10000000, Character)
    CENTER.CFrame = CF(ECH)
    local RAY = CreatePart(3, Effects, "Neon", 0, 1, "Relly red", "Laser01", VT(25,99999,25))
    RAY.Color = C3(0.05,0.05,0.15)
    MakeForm(RAY,"Cyl")
    RAY.CFrame = CF(ECH)
    for i = 1, 75 do
        Swait()
        RAY.Transparency = RAY.Transparency - 1/75
        RAY.Size = RAY.Size - VT(25/75,0,25/75)
        MagicSphere(VT(1,1,1),15,CF(ECH)*CF(MRANDOM(-15,15),MRANDOM(0,100),MRANDOM(-15,15)),C3(1,1,1),VT(0,0,0))
    end
    killnearest(ECH,25,25)
    MagicSphere(VT(0,0,0),55,CF(ECH),C3(0.05,0.05,0.15),VT(2,2,2))
    for i = 1, 25 do
        MagicSphere(VT(1,1,1),i*3,CF(ECH)*CF(MRANDOM(-45,45),MRANDOM(-45,45),MRANDOM(-45,45)),C3(1,1,1),VT(0,0,0))
    end
    CreateSound("168586621", CENTER, 10, 0.8)
    RAY:remove()
    Debris:AddItem(CENTER,5)
end
 
function Star_Cutter()
    local HITFLOOR,HITPOS,NORMAL = Raycast(RootPart.Position, (CF(RootPart.Position, RootPart.Position + VT(0, -1, 0))).lookVector, 7 * Player_Size, Character)
    if HITFLOOR ~= nil then
        ATTACK = true
        Rooted = true
        local GYRO = IT("BodyGyro",RootPart)
        GYRO.D = 100
        GYRO.P = 2000
        GYRO.MaxTorque = VT(0,4000000,0)
        GYRO.cframe = CF(RootPart.Position,Mouse.Hit.p)
        CreateSound("429459101", RightArm, 10, 0.8)
        for i=0, 3.5, 0.1 / Animation_Speed do
            Swait()
            GYRO.cframe = CF(RootPart.Position,Mouse.Hit.p)
            Slice("Thin",0.3,5,RightArm.CFrame * CF(0,-1.1,0) * ANGLES(RAD(MRANDOM(-180,180)),RAD(MRANDOM(-180,180)),RAD(MRANDOM(-180,180))),"Really red",VT(-0.01,0,-0.01))
            RootJoint.C0 = Clerp(RootJoint.C0,ROOTC0 * CF(0, 0, 0 + 0.25 * COS(SINE / 12)) * ANGLES(RAD(4 + 2.5 * SIN(SINE / 12)), RAD(0), RAD(-15 + 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
            Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(0 + 4.5 * SIN(SINE / 12)), RAD(0), RAD(15 - 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
            RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(-45), RAD(0 - 7.5 * SIN(SINE / 12)), RAD(32 + 7.5 * SIN(SINE / 12))) * RIGHTSHOULDERC0, 1 / Animation_Speed)
            LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(5), RAD(0 + 7.5 * SIN(SINE / 12)), RAD(-12 - 7.5 * SIN(SINE / 12))) * LEFTSHOULDERC0, 1 / Animation_Speed)
            RightHip.C0 = Clerp(RightHip.C0, CF(1, -1, -0.01) * ANGLES(RAD(-7.5 * SIN(SINE / 12)), RAD(75), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
            LeftHip.C0 = Clerp(LeftHip.C0, CF(-1, -0.5, -0.5) * ANGLES(RAD(-7.5 * SIN(SINE / 12)), RAD(-90), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
        end
        GYRO:remove()
        for i=0, 0.15, 0.1 / Animation_Speed do
            Swait()
            GYRO.cframe = CF(RootPart.Position,Mouse.Hit.p)
            Slice("Thin",0.3,5,RightArm.CFrame * CF(0,-1.1,0) * ANGLES(RAD(MRANDOM(-180,180)),RAD(MRANDOM(-180,180)),RAD(MRANDOM(-180,180))),"Really red",VT(-0.01,0,-0.01))
            RootJoint.C0 = Clerp(RootJoint.C0,ROOTC0 * CF(0, 0, 0 + 0.25 * COS(SINE / 12)) * ANGLES(RAD(4 + 2.5 * SIN(SINE / 12)), RAD(0), RAD(85 + 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
            Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(0 + 4.5 * SIN(SINE / 12)), RAD(0), RAD(-85 - 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
            RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(0), RAD(0 - 7.5 * SIN(SINE / 12)), RAD(90 + 7.5 * SIN(SINE / 12))) * RIGHTSHOULDERC0, 1 / Animation_Speed)
            LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(5), RAD(0 + 7.5 * SIN(SINE / 12)), RAD(-12 - 7.5 * SIN(SINE / 12))) * LEFTSHOULDERC0, 1 / Animation_Speed)
            RightHip.C0 = Clerp(RightHip.C0, CF(1, -1, -0.01) * ANGLES(RAD(-7.5 * SIN(SINE / 12)), RAD(75), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
            LeftHip.C0 = Clerp(LeftHip.C0, CF(-1, -0.5, -0.5) * ANGLES(RAD(-7.5 * SIN(SINE / 12)), RAD(-90), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
        end
        local BOMBSPOTS = {}
        for i = 1, 25 do
            local SPOT = CreatePart(3, Effects, "Neon", 0, 0, "Relly blue", "Blade", VT(8,1,8))
            SPOT.Color = SKILLTEXTCOLOR
            SPOT.CFrame = RootPart.CFrame*CF((MRANDOM(-15,15)/40)*i,-5,-i*5)
            table.insert(BOMBSPOTS,SPOT)
            MakeForm(SPOT,"Cyl")
        end
        for i=0, 0.2, 0.1 / Animation_Speed do
            Swait()
            RootJoint.C0 = Clerp(RootJoint.C0,ROOTC0 * CF(0, 0, 0 + 0.25 * COS(SINE / 12)) * ANGLES(RAD(4 + 2.5 * SIN(SINE / 12)), RAD(0), RAD(85 + 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
            Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(0 + 4.5 * SIN(SINE / 12)), RAD(0), RAD(-85 - 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
            RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(145), RAD(0 - 7.5 * SIN(SINE / 12)), RAD(-15 + 7.5 * SIN(SINE / 12))) * RIGHTSHOULDERC0, 1 / Animation_Speed)
            LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(-25), RAD(0 + 7.5 * SIN(SINE / 12)), RAD(-12 - 7.5 * SIN(SINE / 12))) * LEFTSHOULDERC0, 1 / Animation_Speed)
            RightHip.C0 = Clerp(RightHip.C0, CF(1, -1, -0.01) * ANGLES(RAD(-7.5 * SIN(SINE / 12)), RAD(75), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
            LeftHip.C0 = Clerp(LeftHip.C0, CF(-1, -0.5, -0.5) * ANGLES(RAD(-7.5 * SIN(SINE / 12)), RAD(-90), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
        end
        ATTACK = false
        Rooted = false
        coroutine.resume(coroutine.create(function()
            Swait(3)
            for i = 1, #BOMBSPOTS do
                if BOMBSPOTS[i] ~= nil then
                    local E = BOMBSPOTS[i]
                    coroutine.resume(coroutine.create(function()
                        local BLADE = CreatePart(3, Effects, "SmoothPlastic", 0, 1, "Relly blue", "Blade", VT(0,0,0))
                        BLADE.Color = SKILLTEXTCOLOR
                        CreateMesh("SpecialMesh", BLADE, "FileMesh", "93108071", "", VT(0.6,1,0.4)*3, VT(0,0,0))
                        CreateSound(HITWEAPONSOUNDS[MRANDOM(1,#HITWEAPONSOUNDS)], BLADE, 4, 0.6)
                        BLADE.CFrame = E.CFrame*CF(0,-3,0)*ANGLES(RAD(MRANDOM(-15,15)),RAD(90),RAD(MRANDOM(-15,15)))
                        for i = 1, 10 do
                            Swait()
                            MagicSphere(VT(1,1,1)/5,65,CF(E.Position)*ANGLES(RAD(MRANDOM(-180,180)),RAD(MRANDOM(-180,180)),RAD(MRANDOM(-180,180)))*CF(0,MRANDOM(3,6),0),C3(1,1,1),VT(0,0,0))
                            killnearest(BLADE.Position,6,80)
                            BLADE.CFrame = BLADE.CFrame*CF(0,0.3,0)
                            BLADE.Transparency = BLADE.Transparency - 0.1
                        end
                        Swait(45)
                        for i = 1, 100 do
                            Swait()
                            BLADE.Transparency = BLADE.Transparency + 0.01
                            E.Transparency = E.Transparency + 0.01
                        end
                        BLADE:remove()
                        E:remove()
                    end))
                end
            end
        end))
    end
end
 
function Supernova()
    local HITFLOOR,HITPOS,NORMAL = Raycast(RootPart.Position, (CF(RootPart.Position, RootPart.Position + VT(0, -1, 0))).lookVector, 7 * Player_Size, Character)
    if HITFLOOR ~= nil then
        local HITBODIES = {}
        ATTACK = true
        Rooted = true
        local ABSOLUTE = CreatePart(3, Effects, "Neon", 0, 1, "Relly red", "Star", VT(0,0,0))
        MakeForm(ABSOLUTE,"Ball")
        CreateSound("429459101", ABSOLUTE, 10, 1)
        for i=0, 4, 0.1 / Animation_Speed do
            Swait()
            ABSOLUTE.Size = ABSOLUTE.Size + VT(0.2,0.2,0.2)
            ABSOLUTE.CFrame = RootPart.CFrame*CF(0,5+(ABSOLUTE.Size.Y/2),0)
            ABSOLUTE.Transparency = ABSOLUTE.Transparency - 0.01
            local CHARGE = CreatePart(3, Effects, "Neon", 0, 0, "Really red", "Star", VT(1,1,1))
            MakeForm(CHARGE,"Ball")
            CHARGE.Color = C3(1,1,1)
            CHARGE.CFrame = CF(RootPart.Position) * CF(MRANDOM(-15,15),-6,MRANDOM(-15,15))
            FireArc(CHARGE,ABSOLUTE.Position,45,45,true)
            RootJoint.C0 = Clerp(RootJoint.C0,ROOTC0 * CF(0, 0, 0 + 0.25 * COS(SINE / 12)) * ANGLES(RAD(4 + 2.5 * SIN(SINE / 12)), RAD(0), RAD(15 + 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
            Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(-25 + 4.5 * SIN(SINE / 12)), RAD(25), RAD(-15 - 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
            RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.25, 1.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(170), RAD(0 - 7.5 * SIN(SINE / 12)), RAD(-12 + 7.5 * SIN(SINE / 12))) * RIGHTSHOULDERC0, 1 / Animation_Speed)
            LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(0), RAD(0 + 7.5 * SIN(SINE / 12)), RAD(-12 - 7.5 * SIN(SINE / 12))) * LEFTSHOULDERC0, 1 / Animation_Speed)
            RightHip.C0 = Clerp(RightHip.C0, CF(1, -1, -0.01) * ANGLES(RAD(-7.5 * SIN(SINE / 12)), RAD(75), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
            LeftHip.C0 = Clerp(LeftHip.C0, CF(-1, -0.5, -0.5) * ANGLES(RAD(-7.5 * SIN(SINE / 12)), RAD(-90), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
        end
        CreateSound("907330103", Head, 10, 1.2)
        for i = 1, 75 do
            Swait()
            RootJoint.C0 = Clerp(RootJoint.C0,ROOTC0 * CF(0, 0, 0 + 0.25 * COS(SINE / 12)) * ANGLES(RAD(4 + 2.5 * SIN(SINE / 12)), RAD(0), RAD(15 + 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
            Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(-25 + 4.5 * SIN(SINE / 12)), RAD(25), RAD(-15 - 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
            RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.25, 1.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(170), RAD(0 - 7.5 * SIN(SINE / 12)), RAD(-12 + 7.5 * SIN(SINE / 12))) * RIGHTSHOULDERC0, 1 / Animation_Speed)
            LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(0), RAD(0 + 7.5 * SIN(SINE / 12)), RAD(-12 - 7.5 * SIN(SINE / 12))) * LEFTSHOULDERC0, 1 / Animation_Speed)
            RightHip.C0 = Clerp(RightHip.C0, CF(1, -1, -0.01) * ANGLES(RAD(-7.5 * SIN(SINE / 12)), RAD(75), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
            LeftHip.C0 = Clerp(LeftHip.C0, CF(-1, -0.5, -0.5) * ANGLES(RAD(-7.5 * SIN(SINE / 12)), RAD(-90), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
        end
        coroutine.resume(coroutine.create(function()
            for i = 1, 13 do
                for e = 1, 8 do
                    Swait()
                    MagicSphere(VT(1,1,1),15,CF(ABSOLUTE.Position)*CF(MRANDOM(-45,45),MRANDOM(-45,45),MRANDOM(-45,45)),C3(1,1,1),VT(0,0,0))
                    CreateSwirl(ABSOLUTE.Size/2,15,CF(HITPOS),true,15,BRICKC"Slime green".Color,VT(i,0.3,i)*2)
                end
                for i = 1, 5 do
                    Slice("Round",0,35,CF(ABSOLUTE.Position)*ANGLES(RAD(MRANDOM(-18,18)),RAD(MRANDOM(-180,180)),RAD(MRANDOM(-18,18))),C3(1,1,1),VT(i,0,i)/3)
                    Slice("Thin",i,55,ABSOLUTE.CFrame * CF(0,-1.1,0) * ANGLES(RAD(MRANDOM(-180,180)),RAD(MRANDOM(-180,180)),RAD(MRANDOM(-180,180))),C3(1,0,0),VT(0,0,0))
                end
                CreateSwirl(ABSOLUTE.Size/2,25,CF(ABSOLUTE.Position),true,-25,BRICKC"Relly red".Color,VT(i,i*2,i))
                CreateSwirl(ABSOLUTE.Size/2,55,CF(ABSOLUTE.Position),true,25,C3(0.05,0.05,0.15),VT(i,i*2,i))
                CreateSound("168586621", ABSOLUTE, 4, 0.8)
                CreateSound("201858144", ABSOLUTE, 10, 0.8)
                killnearest(ABSOLUTE.Position,i*18,i)
                ABSOLUTE.Size = ABSOLUTE.Size*0.9
                MagicSphere(ABSOLUTE.Size,25,CF(ABSOLUTE.Position),BRICKC"Relly red".Color,VT(i,i,i)/1.1)
                MagicSphere(ABSOLUTE.Size,45,CF(ABSOLUTE.Position),C3(0.05,0.05,0.15),VT(i,i,i))
            end
            ABSOLUTE.Transparency = 1
            Debris:AddItem(ABSOLUTE,10)
        end))
        ATTACK = false
        Rooted = false
    end
end
 
local Decal = IT("Decal")
 
function Astral_Hop()
    ATTACK = true
    Rooted = false
    local O1 = CreatePart(3, Effects, "Neon", 0, 1, "Really red", "Warphole", VT(0,0,0))
    O1.CFrame = RootPart.CFrame*CF(0,0,-3)*ANGLES(RAD(90),RAD(0),RAD(0))
    local decal = Decal:Clone()
    decal.Parent = O1
    decal.Face = "Top"
    decal.Texture = "http://www.roblox.com/asset/?id=349165228"
    local decal2 = Decal:Clone()
    decal2.Parent = O1
    decal2.Face = "Bottom"
    decal2.Texture = "http://www.roblox.com/asset/?id=349165228"
    local O2 = CreatePart(3, Effects, "Neon", 0, 1, "Really red", "Warphole", VT(0,0,0))
    local POS = VT(RootPart.Position.X,Mouse.Hit.p.Y+6,RootPart.Position.Z)
    O2.CFrame = CF(Mouse.Hit.p+VT(0,6,0),POS)*ANGLES(RAD(90),RAD(0),RAD(0))
    local ROOT = CreatePart(3, Effects, "Neon", 0, 1, "Really red", "Warphole", VT(0,0,0))
    ROOT.CFrame = CF(O2.Position,RootPart.Position)
    local decal = Decal:Clone()
    decal.Parent = O2
    decal.Face = "Top"
    decal.Texture = "http://www.roblox.com/asset/?id=349165228"
    local decal2 = Decal:Clone()
    decal2.Parent = O2
    decal2.Face = "Bottom"
    decal2.Texture = "http://www.roblox.com/asset/?id=349165228"
    CreateSound("84005018", O1, 10, 0.7)
    CreateSound("84005018", O2, 10, 0.7)
    for i = 1, 75 do
        Swait()
        O1.Size = O1.Size + VT(0.1,0,0.1)
        O1.CFrame = RootPart.CFrame*CF(0,0,-3)*ANGLES(RAD(90),RAD(i),RAD(0))
        O2.Size = O2.Size + VT(0.1,0,0.1)
        O2.CFrame = O2.CFrame*ANGLES(RAD(0),RAD(i),RAD(0))
        RootJoint.C0 = Clerp(RootJoint.C0,ROOTC0 * CF(0, 0, 0 + 0.25 * COS(SINE / 12)) * ANGLES(RAD(4 + 2.5 * SIN(SINE / 12)), RAD(0), RAD(5 + 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
        Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(0 + 4.5 * SIN(SINE / 12)), RAD(0), RAD(-5 - 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
        RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(90), RAD(0 - 2.5 * SIN(SINE / 12)), RAD(5 + 7.5 * SIN(SINE / 12))) * RIGHTSHOULDERC0, 1 / Animation_Speed)
        LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(90), RAD(0 + 2.5 * SIN(SINE / 12)), RAD(-5 - 7.5 * SIN(SINE / 12))) * LEFTSHOULDERC0, 1 / Animation_Speed)
        RightHip.C0 = Clerp(RightHip.C0, CF(1, -1, -0.01) * ANGLES(RAD(-2.5 * SIN(SINE / 12)), RAD(75), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
        LeftHip.C0 = Clerp(LeftHip.C0, CF(-1, -0.5, -0.5) * ANGLES(RAD(-2.5 * SIN(SINE / 12)), RAD(-90), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
    end
    Rooted = true
    UNANCHOR = false
    RootPart.Anchored = true
    VALUE1 = true
    for i = 1, 15 do
        Transparency(i/15)
        Swait()
        RootPart.CFrame = RootPart.CFrame*CF(0,0,-0.13)
        RootJoint.C0 = Clerp(RootJoint.C0,ROOTC0 * CF(0, 0, 0 + 0.25 * COS(SINE / 12)) * ANGLES(RAD(16 + 2.5 * SIN(SINE / 12)), RAD(0), RAD(5 + 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
        Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(-15 + 4.5 * SIN(SINE / 12)), RAD(0), RAD(-5 - 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
        RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(-15), RAD(0 - 2.5 * SIN(SINE / 12)), RAD(5 + 7.5 * SIN(SINE / 12))) * RIGHTSHOULDERC0, 1 / Animation_Speed)
        LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(-15), RAD(0 + 2.5 * SIN(SINE / 12)), RAD(-5 - 7.5 * SIN(SINE / 12))) * LEFTSHOULDERC0, 1 / Animation_Speed)
        RightHip.C0 = Clerp(RightHip.C0, CF(1, -1, -0.01) * ANGLES(RAD(-2.5 * SIN(SINE / 12)), RAD(75), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
        LeftHip.C0 = Clerp(LeftHip.C0, CF(-1, -0.5, -0.5) * ANGLES(RAD(-2.5 * SIN(SINE / 12)), RAD(-90), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
    end
    RootPart.CFrame = ROOT.CFrame
    ROOT:remove()
    for i = 1, 15 do
        Transparency(1-(i/15))
        Swait()
        RootPart.CFrame = RootPart.CFrame*CF(0,0,-0.5)
        RootJoint.C0 = Clerp(RootJoint.C0,ROOTC0 * CF(0, 0, 0 + 0.25 * COS(SINE / 12)) * ANGLES(RAD(16 + 2.5 * SIN(SINE / 12)), RAD(0), RAD(5 + 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
        Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(-15 + 4.5 * SIN(SINE / 12)), RAD(0), RAD(-5 - 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
        RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(-15), RAD(0 - 2.5 * SIN(SINE / 12)), RAD(5 + 7.5 * SIN(SINE / 12))) * RIGHTSHOULDERC0, 1 / Animation_Speed)
        LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(-15), RAD(0 + 2.5 * SIN(SINE / 12)), RAD(-5 - 7.5 * SIN(SINE / 12))) * LEFTSHOULDERC0, 1 / Animation_Speed)
        RightHip.C0 = Clerp(RightHip.C0, CF(1, -1, -0.01) * ANGLES(RAD(-2.5 * SIN(SINE / 12)), RAD(75), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
        LeftHip.C0 = Clerp(LeftHip.C0, CF(-1, -0.5, -0.5) * ANGLES(RAD(-2.5 * SIN(SINE / 12)), RAD(-90), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
    end
    VALUE1 = false
    coroutine.resume(coroutine.create(function()
        for i = 1, 75 do
            Swait()
            O1.Size = O1.Size - VT(0.1,0,0.1)
            O1.CFrame = O1.CFrame*ANGLES(RAD(0),RAD(i),RAD(0))
            O2.Size = O2.Size - VT(0.1,0,0.1)
            O2.CFrame = O2.CFrame*ANGLES(RAD(0),RAD(i),RAD(0))
        end
        O1:remove()
        O2:remove()
    end))
    UNANCHOR = true
    RootPart.Anchored = false
    ATTACK = false
    Rooted = false
end
 
--//=================================\\
--||      ASSIGN THINGS TO KEYS
--\\=================================//
 
function MouseDown(Mouse)
    if ATTACK == false then
    end
end
 
function MouseUp(Mouse)
HOLD = false
end
 
function KeyDown(Key)
    KEYHOLD = true
    if Key == "z" and ATTACK == false then
        Lunar_Blast()
    end
 
    if Key == "b" and ATTACK == false then
        Star_Cutter()
    end
 
    if Key == "c" and ATTACK == false then
        Supernova()
    end
 
    if Key == "q" and ATTACK == false then
        Astral_Hop()
    end
end
 
function KeyUp(Key)
    KEYHOLD = false
end
 
    Mouse.Button1Down:connect(function(NEWKEY)
        MouseDown(NEWKEY)
    end)
    Mouse.Button1Up:connect(function(NEWKEY)
        MouseUp(NEWKEY)
    end)
    Mouse.KeyDown:connect(function(NEWKEY)
        KeyDown(NEWKEY)
    end)
    Mouse.KeyUp:connect(function(NEWKEY)
        KeyUp(NEWKEY)
    end)
 
--//=================================\\
--\\=================================//
 
 
function unanchor()
    if UNANCHOR == true then
        g = Character:GetChildren()
        for i = 1, #g do
            if g[i].ClassName == "Part" then
                g[i].Anchored = false
            end
        end
    end
end
 
 
--//=================================\\
--||    WRAP THE WHOLE SCRIPT UP
--\\=================================//
 
Humanoid.Changed:connect(function(Jump)
    if Jump == "Jump" and (Disable_Jump == true) then
        Humanoid.Jump = false
    end
end)
 
Humanoid.HipHeight = 2
Head:ClearAllChildren()
local FF = IT("ForceField",Character)
FF.Visible = false
Speed = 35
 
function refit()
    RootJoint.Parent = RootPart
    Neck.Parent = Torso
    RightShoulder.Parent = Torso
    LeftShoulder.Parent = Torso
    RightHip.Parent = Torso
    LeftHip.Parent = Torso
    RootPart.Parent = Character
    LeftArm.Parent = Character
    RightArm.Parent = Character
    RightLeg.Parent = Character
    LeftLeg.Parent = Character
    Torso.Parent = Character
    Head.Parent = Character
end
 
local FOUNDFORGOTTEN = false
 
while true do
    Swait()
    ANIMATE.Parent = nil
    local IDLEANIMATION = Humanoid:LoadAnimation(ROBLOXIDLEANIMATION)
    IDLEANIMATION:Play()
    SINE = SINE + CHANGE
    local TORSOVELOCITY = (RootPart.Velocity * VT(1, 0, 1)).magnitude
    local TORSOVERTICALVELOCITY = RootPart.Velocity.y
    local LV = Torso.CFrame:pointToObjectSpace(Torso.Velocity - Torso.Position)
    local HITFLOOR,HITPOS,NORMAL = Raycast(RootPart.Position, (CF(RootPart.Position, RootPart.Position + VT(0, -1, 0))).lookVector, 7 * Player_Size, Character)
    if ATTACK == false then
        if TORSOVELOCITY < 1 then
            RootJoint.C0 = Clerp(RootJoint.C0,ROOTC0 * CF(0, 0, 0 + 0.25 * COS(SINE / 12)) * ANGLES(RAD(4 + 2.5 * SIN(SINE / 12)), RAD(0), RAD(5 + 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
            Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(0 + 4.5 * SIN(SINE / 12)), RAD(0), RAD(-5 - 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
            RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(0), RAD(0 - 2.5 * SIN(SINE / 12)), RAD(5 + 7.5 * SIN(SINE / 12))) * RIGHTSHOULDERC0, 1 / Animation_Speed)
            LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(0), RAD(0 + 2.5 * SIN(SINE / 12)), RAD(-5 - 7.5 * SIN(SINE / 12))) * LEFTSHOULDERC0, 1 / Animation_Speed)
            RightHip.C0 = Clerp(RightHip.C0, CF(1, -1, -0.01) * ANGLES(RAD(-2.5 * SIN(SINE / 12)), RAD(75), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
            LeftHip.C0 = Clerp(LeftHip.C0, CF(-1, -0.5, -0.5) * ANGLES(RAD(-2.5 * SIN(SINE / 12)), RAD(-90), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
        elseif TORSOVELOCITY > 1 then
            RootJoint.C0 = Clerp(RootJoint.C0,ROOTC0 * CF(0, 0, 0 + 0.25 * COS(SINE / 12)) * ANGLES(RAD(25 + 2.5 * SIN(SINE / 12)), RAD(0), RAD(5 + 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
            Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0, 0, 0 + ((1) - 1)) * ANGLES(RAD(-25 + 4.5 * SIN(SINE / 12)), RAD(0), RAD(-5 - 2.5 * SIN(SINE / 12))), 1 / Animation_Speed)
            RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(-25), RAD(0 - 2.5 * SIN(SINE / 12)), RAD(15 + 7.5 * SIN(SINE / 12))) * RIGHTSHOULDERC0, 1 / Animation_Speed)
            LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5, 0.5 + 0.25 * COS(SINE / 12), 0) * ANGLES(RAD(-25), RAD(0 + 2.5 * SIN(SINE / 12)), RAD(-15 - 7.5 * SIN(SINE / 12))) * LEFTSHOULDERC0, 1 / Animation_Speed)
            RightHip.C0 = Clerp(RightHip.C0, CF(1, -1, -0.01) * ANGLES(RAD(-25-2.5 * SIN(SINE / 12)), RAD(75), RAD(0)) * ANGLES(RAD(-8 - 5.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
            LeftHip.C0 = Clerp(LeftHip.C0, CF(-1, -0.5, -0.5) * ANGLES(RAD(-2.5 * SIN(SINE / 12)), RAD(-90), RAD(0)) * ANGLES(RAD(-8 - 2.5 * SIN(SINE / 12)), RAD(0), RAD(0)), 1 / Animation_Speed)
        end
    end
    unanchor()
    Humanoid.MaxHealth = "inf"
    Humanoid.Health = "inf"
    if Rooted == false then
        Disable_Jump = false
        Humanoid.WalkSpeed = Speed
    elseif Rooted == true then
        Disable_Jump = true
        Humanoid.WalkSpeed = 0
    end
    for _, c in pairs(Character:GetChildren()) do
        if c.ClassName == "Part" then
            c.Material = "Neon"
            if c:FindFirstChildOfClass("ParticleEmitter") then
                c:FindFirstChildOfClass("ParticleEmitter"):remove()
            end
            if c == Torso then
                c.Color = C3(0,0,0)
            elseif c == RightArm then
                c.Color = C3(0.05,0.05,0.15)
            elseif c == LeftArm then
                c.Color = C3(0.05,0.05,0.15)
            elseif c == RightLeg then
                c.Color = C3(0,0,0.05)
            elseif c == LeftLeg then
                c.Color = C3(0,0,0.05)
            elseif c == Head then
                if c:FindFirstChild("Dominus") == nil then
                    local M = CreateMesh("SpecialMesh", c, "FileMesh", "162384581", "162384608", VT(1,1,1)*1.1, VT(0,0,0))
                    M.Name = "Dominus"
                end
                if c:FindFirstChild("face") then
                    c.face:remove()
                end
            end
        elseif c.ClassName == "Shirt" or c.ClassName == "Pants" or c.ClassName == "CharacterMesh" or c.ClassName == "Accessory" or c.Name == "Body Colors" then
            c:remove()
        end
    end
    FF.Parent = Character
    sick.Parent = Character
    refit()
    script.Parent = WEAPONGUI
    Character.Parent = workspace
    Humanoid.PlatformStand = false
    Humanoid.Name = "Astra"
    for _, c in pairs(game.Players:GetChildren()) do
        if c.Character ~= nil then
            if c.Character.Parent ~= workspace and c.Character.Parent ~= nil then
                c.Character:BreakJoints()
            end
        end
    end
    FOUNDFORGOTTEN = false
    Humanoid.DisplayDistanceType = "None"
    for _, c in pairs(workspace:GetChildren()) do
        if c.ClassName == "Model" then
            for _, q in pairs(c:GetChildren()) do
                if q.Name == ("Forgotten Dominus") then
                    FOUNDFORGOTTEN = true
                end
            end
        end
    end
    if FOUNDFORGOTTEN == true then
        sick:Stop()
    else
        sick.Playing = true
    end
    if VALUE1 == false then
        MagicSphere(VT(1,1,1)/5,35,CF(Torso.Position)*ANGLES(RAD(MRANDOM(-180,180)),RAD(MRANDOM(-180,180)),RAD(MRANDOM(-180,180)))*CF(0,MRANDOM(3,6),0),C3(1,1,1),VT(0,0,0))
    end
end
 
--//=================================\\
--\\=================================//
 
 
 
 
 
--//====================================================\\--
--||                     END OF SCRIPT
--\\====================================================//--
end)

Section:NewButton("Lustris", "Made by yanros74", function()
-- Shadow Blade Edit by MappleGalexy(MapleGalaxy) --
-- I'll Fucking Find You --
Player=game:GetService("Players").LocalPlayer
Character=Player.Character 
PlayerGui=Player.PlayerGui
Backpack=Player.Backpack 
Torso=Character.Torso 
Head=Character.Head 
Humanoid=Character.Humanoid
LeftArm=Character["Left Arm"] 
LeftLeg=Character["Left Leg"] 
RightArm=Character["Right Arm"] 
RightLeg=Character["Right Leg"] 
cam=game.Workspace.CurrentCamera
LS=Torso["Left Shoulder"] 
LH=Torso["Left Hip"] 
RS=Torso["Right Shoulder"] 
RH=Torso["Right Hip"] 
Face = Head.face
Neck=Torso.Neck
it=Instance.new
attacktype=1
vt=Vector3.new
cf=CFrame.new
script.Name = "MagicBlade"
euler=CFrame.fromEulerAnglesXYZ
angles=CFrame.Angles
cloaked=false
necko=cf(0, 1, 0, -1, -0, -0, 0, 0, 1, 0, 1, 0)
necko2=cf(0, -0.5, 0, -1, -0, -0, 0, 0, 1, 0, 1, 0)
LHC0=cf(-1,-1,0,-0,-0,-1,0,1,0,1,0,0)
LHC1=cf(-0.5,1,0,-0,-0,-1,0,1,0,1,0,0)
RHC0=cf(1,-1,0,0,0,1,0,1,0,-1,-0,-0)
RHC1=cf(0.5,1,0,0,0,1,0,1,0,-1,-0,-0)
RootPart=Character.HumanoidRootPart
RootJoint=RootPart.RootJoint
RootCF=euler(-1.57,0,3.14)
attack = false 
bounce=false
cooldown=false
deeznuts=false
attackdebounce = false 
deb=false
equipped=true
hand=false
MMouse=nil
combo=0
mana=0
trispeed=.2
attackmode='none'
local idle=0
local Anim="Idle"
local Effects={}
local gun=false
local shoot=false
player=nil 
mana=0
cam = workspace.CurrentCamera
ZTarget = nil
RocketTarget = nil
local m = Instance.new("Model",Character)
m.Name = "WeaponModelz"

local SHEZ = Instance.new("Sound",Character.HumanoidRootPart)SHEZ.SoundId = "rbxassetid://656541219" SHEZ.Looped = true SHEZ.Volume = 2 SHEZ:Play()
mouse=Player:GetMouse()
--save shoulders 
RSH, LSH=nil, nil 
--welds 
RW, LW=Instance.new("Weld"), Instance.new("Weld") 
RW.Name="Right Shoulder" LW.Name="Left Shoulder"
LH=Torso["Left Hip"]
RH=Torso["Right Hip"]
TorsoColor=Torso.BrickColor
function NoOutline(Part)
Part.TopSurface,Part.BottomSurface,Part.LeftSurface,Part.RightSurface,Part.FrontSurface,Part.BackSurface = 10,10,10,10,10,10
end
player=Player 
ch=Character
RSH=ch.Torso["Right Shoulder"] 
LSH=ch.Torso["Left Shoulder"] 
-- 
RSH.Parent=nil 
LSH.Parent=nil 
-- 
RW.Name="Right Shoulder"
RW.Part0=ch.Torso 
RW.C0=cf(1.5, 0.5, 0) --* CFrame.fromEulerAnglesXYZ(1.3, 0, -0.5) 
RW.C1=cf(0, 0.5, 0) 
RW.Part1=ch["Right Arm"] 
RW.Parent=ch.Torso 
-- 
LW.Name="Left Shoulder"
LW.Part0=ch.Torso 
LW.C0=cf(-1.5, 0.5, 0) --* CFrame.fromEulerAnglesXYZ(1.7, 0, 0.8) 
LW.C1=cf(0, 0.5, 0) 
LW.Part1=ch["Left Arm"] 
LW.Parent=ch.Torso 

	function swait(num)
    if num==0 or num==nil then
    game:service'RunService'.Heartbeat:wait(0)
    else
    for i=0,num do
    game:service'RunService'.Heartbeat:wait(0)
    end
    end
	end
	
	function nooutline(part)
		part.TopSurface,part.BottomSurface,part.LeftSurface,part.RightSurface,part.FrontSurface,part.BackSurface = 10,10,10,10,10,10
	end
	
	function part(formfactor,parent,material,reflectance,transparency,brickcolor,name,size)
		local fp=it("Part")
		fp.formFactor=formfactor
		fp.Parent=parent
		fp.Reflectance=reflectance
		fp.Transparency=transparency
		fp.CanCollide=false
		fp.Locked=true
		fp.BrickColor=BrickColor.new(tostring(brickcolor))
		fp.Name=name
		fp.Size=size
		fp.Position=Character.Torso.Position
		nooutline(fp)
		fp.Material=material
		fp:BreakJoints()
		return fp
	end
	
	function ppart(formfactor,parent,reflectance,transparency,brickcolor,name,size)
		local fp = it("Part")
		fp.formFactor = formfactor 
		fp.Parent = parent
		fp.Reflectance = reflectance
		fp.Transparency = transparency
		fp.CanCollide = false 
		fp.Locked=true
		fp.BrickColor = brickcolor
		fp.Name = name
		fp.Size = size
		fp.Position = EffectPart.Position 
		NoOutline(fp)
		fp.Material="Neon"
		fp:BreakJoints()
		return fp 
	end 
	
	function wweld(parent,part0,part1,c0)
		local weld=it("Weld") 
		weld.Parent=parent	
		weld.Part0=part0 
		weld.Part1=part1 
		weld.C0=c0
		return weld
	end
	
	function mesh(Mesh,part,meshtype,meshid,offset,scale)
		local mesh=it(Mesh)
		mesh.Parent=part
		if Mesh=="SpecialMesh" then
			mesh.MeshType=meshtype
			mesh.MeshId=meshid
		end
		mesh.Offset=offset
		mesh.Scale=scale
		return mesh
	end
	
	function decal(part,face,texture,transparency,shiny,specular,name)
		local d=it("Decal",part)
		d.Shiny=shiny
		d.Face=face
		d.Specular=specular
		d.Transparency=transparency
		d.Texture=texture
		d.Name=name
		return d
	end
	
	function weld(parent,part0,part1,c0,c1)
		local weld=it("Weld")
		weld.Parent=parent
		weld.Part0=part0
		weld.Part1=part1
		weld.C0=c0
		weld.C1=c1
		return weld
	end
	
Humanoid.Name = "Noctis"
local SH = Instance.new("Sound")
local list = {}
	
so = function(id,par,vol,pit) 
coroutine.resume(coroutine.create(function()
local sou = SH:clone() sou.Parent = par or workspace
sou.Volume=vol
sou.Pitch=pit or 1
sou.SoundId=id
sou:play() 
game:GetService("Debris"):AddItem(sou,15)
end))
end
 
function clerp(a,b,t) 
local qa = {QuaternionFromCFrame(a)}
local qb = {QuaternionFromCFrame(b)} 
local ax, ay, az = a.x, a.y, a.z 
local bx, by, bz = b.x, b.y, b.z
local _t = 1-t
return QuaternionToCFrame(_t*ax + t*bx, _t*ay + t*by, _t*az + t*bz,QuaternionSlerp(qa, qb, t)) 
end 
 
function QuaternionFromCFrame(cf) 
local mx, my, mz, m00, m01, m02, m10, m11, m12, m20, m21, m22 = cf:components() 
local trace = m00 + m11 + m22 
if trace > 0 then 
local s = math.sqrt(1 + trace) 
local recip = 0.5/s 
return (m21-m12)*recip, (m02-m20)*recip, (m10-m01)*recip, s*0.5 
else 
local i = 0 
if m11 > m00 then
i = 1
end
if m22 > (i == 0 and m00 or m11) then 
i = 2 
end 
if i == 0 then 
local s = math.sqrt(m00-m11-m22+1) 
local recip = 0.5/s 
return 0.5*s, (m10+m01)*recip, (m20+m02)*recip, (m21-m12)*recip 
elseif i == 1 then 
local s = math.sqrt(m11-m22-m00+1) 
local recip = 0.5/s 
return (m01+m10)*recip, 0.5*s, (m21+m12)*recip, (m02-m20)*recip 
elseif i == 2 then 
local s = math.sqrt(m22-m00-m11+1) 
local recip = 0.5/s return (m02+m20)*recip, (m12+m21)*recip, 0.5*s, (m10-m01)*recip 
end 
end 
end
 
function QuaternionToCFrame(px, py, pz, x, y, z, w) 
local xs, ys, zs = x + x, y + y, z + z 
local wx, wy, wz = w*xs, w*ys, w*zs 
local xx = x*xs 
local xy = x*ys 
local xz = x*zs 
local yy = y*ys 
local yz = y*zs 
local zz = z*zs 
return CFrame.new(px, py, pz,1-(yy+zz), xy - wz, xz + wy,xy + wz, 1-(xx+zz), yz - wx, xz - wy, yz + wx, 1-(xx+yy)) 
end
 
function QuaternionSlerp(a, b, t) 
local cosTheta = a[1]*b[1] + a[2]*b[2] + a[3]*b[3] + a[4]*b[4] 
local startInterp, finishInterp; 
if cosTheta >= 0.0001 then 
if (1 - cosTheta) > 0.0001 then 
local theta = math.acos(cosTheta) 
local invSinTheta = 1/math.sin(theta) 
startInterp = math.sin((1-t)*theta)*invSinTheta 
finishInterp = math.sin(t*theta)*invSinTheta  
else 
startInterp = 1-t 
finishInterp = t 
end 
else 
if (1+cosTheta) > 0.0001 then 
local theta = math.acos(-cosTheta) 
local invSinTheta = 1/math.sin(theta) 
startInterp = math.sin((t-1)*theta)*invSinTheta 
finishInterp = math.sin(t*theta)*invSinTheta 
else 
startInterp = t-1 
finishInterp = t 
end 
end 
return a[1]*startInterp + b[1]*finishInterp, a[2]*startInterp + b[2]*finishInterp, a[3]*startInterp + b[3]*finishInterp, a[4]*startInterp + b[4]*finishInterp 
end

function rayCast(Pos, Dir, Max, Ignore)  -- Origin Position , Direction, MaxDistance , IgnoreDescendants
return game:service("Workspace"):FindPartOnRay(Ray.new(Pos, Dir.unit * (Max or 999.999)), Ignore) 
end 

Damagefunc=function(Part,hit,minim,maxim,knockback,Type,Property,Delay,KnockbackType,decreaseblock)
        if hit.Parent==nil then
                return
        end
        local h=hit.Parent:FindFirstChild("Humanoid")
        for _,v in pairs(hit.Parent:children()) do
        if v:IsA("Humanoid") then
        h=v
        end
        end
        if hit.Parent.Parent:FindFirstChild("Torso")~=nil then
        h=hit.Parent.Parent:FindFirstChild("Humanoid")
        end
        if hit.Parent.className=="Hat" then
        hit=hit.Parent.Parent:findFirstChild("Head")
        end
        if h~=nil and hit.Parent.Name~=Character.Name and hit.Parent:FindFirstChild("Torso")~=nil then
        if hit.Parent:findFirstChild("DebounceHit")~=nil then if hit.Parent.DebounceHit.Value==true then return end end
        --[[                if game.Players:GetPlayerFromCharacter(hit.Parent)~=nil then
                        return
                end]]
--                        hs(hit,1.2) 
                        local c=Instance.new("ObjectValue")
                        c.Name="creator"
                        c.Value=game:service("Players").LocalPlayer
                        c.Parent=h
                        game:GetService("Debris"):AddItem(c,.5)
                local Damage=math.random(minim,maxim)
--                h:TakeDamage(Damage)
                local  blocked=false
                local  block=hit.Parent:findFirstChild("Block")
                if block~=nil then
                print(block.className)
                if block.className=="NumberValue" then
                if block.Value>0 then
                blocked=true
                if decreaseblock==nil then
                block.Value=block.Value-1
                end
                end
                end
                if block.className=="IntValue" then
                if block.Value>0 then
                blocked=true
                if decreaseblock~=nil then
                block.Value=block.Value-1
                end
                end
                end
                end
                if blocked==false then
--                h:TakeDamage(Damage)
                h.Health=h.Health-Damage
                ShowDamage((Part.CFrame * CFrame.new(math.random(-5,5), math.random(-5,5), math.random(-5,5)+ (Part.Size.Z / 2)).p + Vector3.new(0, 1.5, 0)), -Damage, 1.5, Part.BrickColor.Color)
                else
                h.Health=h.Health-(Damage/2)
                ShowDamage((Part.CFrame * CFrame.new(0, 0, (Part.Size.Z / 2)).p + Vector3.new(0, 1.5, 0)), -Damage, 1.5, BrickColor.new("Bright blue").Color)
                end
                if Type=="Knockdown" then
                local hum=hit.Parent.Humanoid
hum.PlatformStand=true
coroutine.resume(coroutine.create(function(HHumanoid)
swait(1)
HHumanoid.PlatformStand=false
end),hum)
                local angle=(hit.Position-(Property.Position+Vector3.new(0,0,0))).unit
--hit.CFrame=CFrame.new(hit.Position,Vector3.new(angle.x,hit.Position.y,angle.z))*CFrame.fromEulerAnglesXYZ(math.pi/4,0,0)
local bodvol=Instance.new("BodyVelocity")
bodvol.velocity=angle*knockback
bodvol.P=5000
bodvol.maxForce=Vector3.new(8e+003, 8e+003, 8e+003)
bodvol.Parent=hit
local rl=Instance.new("BodyAngularVelocity")
rl.P=3000
rl.maxTorque=Vector3.new(500000,500000,500000)*50000000000000
rl.angularvelocity=Vector3.new(math.random(-10,10),math.random(-10,10),math.random(-10,10))
rl.Parent=hit
game:GetService("Debris"):AddItem(bodvol,.5)
game:GetService("Debris"):AddItem(rl,.5)
                elseif Type=="Normal" then
                local vp=Instance.new("BodyVelocity")
                vp.P=500
                vp.maxForce=Vector3.new(math.huge,0,math.huge)
--                vp.velocity=Character.Torso.CFrame.lookVector*Knockback
                if KnockbackType==1 then
                vp.velocity=Property.CFrame.lookVector*knockback+Property.Velocity/1.05
                elseif KnockbackType==2 then
                vp.velocity=Property.CFrame.lookVector*knockback
                end
                if knockback>0 then
                        vp.Parent=hit.Parent.Torso
                end
                game:GetService("Debris"):AddItem(vp,.5)
                elseif Type=="Up" then
                local bodyVelocity=Instance.new("BodyVelocity")
                bodyVelocity.velocity=vt(0,60,0)
                bodyVelocity.P=5000
                bodyVelocity.maxForce=Vector3.new(8e+003, 8e+003, 8e+003)
                bodyVelocity.Parent=hit
                game:GetService("Debris"):AddItem(bodyVelocity,1)
                local rl=Instance.new("BodyAngularVelocity")
                rl.P=3000
                rl.maxTorque=Vector3.new(500000,500000,500000)*50000000000000
                rl.angularvelocity=Vector3.new(math.random(-30,30),math.random(-30,30),math.random(-30,30))
                rl.Parent=hit
                game:GetService("Debris"):AddItem(rl,.5)
                elseif Type=="Snare" then
                local bp=Instance.new("BodyPosition")
                bp.P=2000
                bp.D=100
                bp.maxForce=Vector3.new(math.huge,math.huge,math.huge)
                bp.position=hit.Parent.Torso.Position
                bp.Parent=hit.Parent.Torso
                game:GetService("Debris"):AddItem(bp,1)
                elseif Type=="Target" then
	            local Targetting = false
                if Targetting==false then
                ZTarget=hit.Parent.Torso
                coroutine.resume(coroutine.create(function(Part) 
                so("http://www.roblox.com/asset/?id=15666462",Part,1,1.5) 
                swait(5)
                so("http://www.roblox.com/asset/?id=15666462",Part,1,1.5) 
                end),ZTarget)
                local TargHum=ZTarget.Parent:findFirstChild("Humanoid")
                local  targetgui=Instance.new("BillboardGui")
                targetgui.Parent=ZTarget
                targetgui.Size=UDim2.new(10,100,10,100)
                local targ=Instance.new("ImageLabel")
                targ.Parent=targetgui
                targ.BackgroundTransparency=1
                targ.Image="rbxassetid://4834067"
                targ.Size=UDim2.new(1,0,1,0)
                cam.CameraType="Scriptable"
                cam.CoordinateFrame=CFrame.new(Head.CFrame.p,ZTarget.Position)
                local dir=Vector3.new(cam.CoordinateFrame.lookVector.x,0,cam.CoordinateFrame.lookVector.z)
                workspace.CurrentCamera.CoordinateFrame=CFrame.new(Head.CFrame.p,ZTarget.Position)
                Targetting=true
                RocketTarget=ZTarget
                for i=1,Property do
                --while Targetting==true and Humanoid.Health>0 and Character.Parent~=nil do
                if Humanoid.Health>0 and Character.Parent~=nil and TargHum.Health>0 and TargHum.Parent~=nil and Targetting==true then
                swait()
                end
                --workspace.CurrentCamera.CoordinateFrame=CFrame.new(Head.CFrame.p,Head.CFrame.p+rmdir*100)
                cam.CoordinateFrame=CFrame.new(Head.CFrame.p,ZTarget.Position)
                dir=Vector3.new(cam.CoordinateFrame.lookVector.x,0,cam.CoordinateFrame.lookVector.z)
                cam.CoordinateFrame=CFrame.new(Head.CFrame.p,ZTarget.Position)*cf(0,5,10)*euler(-0.3,0,0)
                end
                Targetting=false
                RocketTarget=nil
                targetgui.Parent=nil
                cam.CameraType="Custom"
                end
                end
                        c=Instance.new("ObjectValue")
                        c.Name="creator"
                        c.Value=Player
                        c.Parent=h
                        game:GetService("Debris"):AddItem(c,.5)
        end
end


function ShowDamage(Pos, Text, Time, Color)
	local Rate = (1 / 30)
	local Pos = (Pos or Vector3.new(0, 0, 0))
	local Text = (Text or "")
	local Time = (Time or 2)
	local Color = (Color or Color3.new(1, 0, 0))
	local EffectPart = part("Custom",workspace,"SmoothPlastic",0,1,BrickColor.new(Color),"Effect",vt(0,0,0))
	EffectPart.Anchored = true
	local BillboardGui = Instance.new("BillboardGui")
	BillboardGui.Size = UDim2.new(3, 0, 3, 0)
	BillboardGui.Adornee = EffectPart
	local TextLabel = Instance.new("TextLabel")
	TextLabel.BackgroundTransparency = 1
	TextLabel.Size = UDim2.new(1, 0, 1, 0)
	TextLabel.Text = Text
	TextLabel.TextColor3 = Color
	TextLabel.TextScaled = true
	TextLabel.Font = Enum.Font.ArialBold
	TextLabel.Parent = BillboardGui
	BillboardGui.Parent = EffectPart
	game.Debris:AddItem(EffectPart, (Time + 0.1))
	EffectPart.Parent = game:GetService("Workspace")
	Delay(0, function()
		local Frames = (Time / Rate)
		for Frame = 1, Frames do
			wait(Rate)
			local Percent = (Frame / Frames)
			EffectPart.CFrame = CFrame.new(Pos) + Vector3.new(0, Percent, 0)
			TextLabel.TextTransparency = Percent
		end
		if EffectPart and EffectPart.Parent then
			EffectPart:Destroy()
		end
	end)
end

handle=part(Enum.FormFactor.Custom,m,Enum.Material.SmoothPlastic,0,0,"Black","Handle",Vector3.new(0.200000003, 1.61857152, 0.200000003))
handleweld=weld(m,Character["Right Arm"],handle,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(0.995889783, -0.101109691, 0.0468789339, -5.23798153e-005, 0.99999994, -0.000210702419, -6.36925748e-008, -0.000210702419, -0.99999994, -1, -5.23798008e-005, 7.47295417e-008))
handleweld.Name = "MagicWeld"
mesh("CylinderMesh",handle,"","",Vector3.new(0, 0, 0),Vector3.new(0.857142806, 1, 0.857142746))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.SmoothPlastic,0,0,"Black","SwordPart",Vector3.new(0.200000003, 0.257142872, 0.911428571))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-0.00982296467, -0.128642559, 5.57254982, -1.21753502e-007, -2.87620594e-010, 1, -1, -1.04306673e-006, -1.2175461e-007, 1.04306673e-006, -1, -2.87123214e-010))
mesh("SpecialMesh",Part,Enum.MeshType.Wedge,"",Vector3.new(0, 0, 0),Vector3.new(0.571428537, 1, 1))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(0.200000003, 3.74285722, 0.571428657))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(0.0100114346, 3.24283266, 2.64644623e-005, -2.98713599e-006, -1.63886575e-008, -1, -1.18017197e-005, -0.99999994, 1.64265153e-008, -0.99999994, 1.18017197e-005, 2.98713007e-006))
mesh("BlockMesh",Part,"","",Vector3.new(0, 0, 0),Vector3.new(0.285714298, 1, 1))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.SmoothPlastic,0,0,"Black","SwordPart",Vector3.new(0.200000003, 3.74285722, 0.514285743))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(0.00896048546, 3.24313331, -6.2584877e-006, -2.62832918e-006, -1.58840017e-008, -1, -1.16825104e-005, -0.99999994, 1.59122848e-008, -0.99999994, 1.16825104e-005, 2.62831986e-006))
mesh("BlockMesh",Part,"","",Vector3.new(0, 0, 0),Vector3.new(0.571428537, 1, 1))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.SmoothPlastic,0,0,"Black","SwordPart",Vector3.new(0.200000003, 0.914285779, 0.254285723))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-0.0080575943, -5.57459974, 0.127099097, -7.20826961e-007, -1.18548371e-009, 1, 6.25863322e-007, 1, 1.18891563e-009, -1, 6.25863322e-007, -7.20827984e-007))
mesh("SpecialMesh",Part,Enum.MeshType.Wedge,"",Vector3.new(0, 0, 0),Vector3.new(0.571428537, 1, 1))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(0.200000003, 0.942857206, 0.28285715))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-0.00858414173, -5.58866072, 0.142816901, -5.41048905e-007, -8.99582631e-010, 1, -5.96046448e-007, 0.99999994, 9.00953978e-010, -0.99999994, -5.96046448e-007, -5.41057148e-007))
mesh("SpecialMesh",Part,Enum.MeshType.Wedge,"",Vector3.new(0, 0, 0),Vector3.new(0.285714298, 1, 1))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(0.200000003, 0.285714328, 0.940000057))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-0.011053443, -0.142930448, 5.58944941, 2.97432763e-007, 3.64387631e-010, 1, -1, 6.25863322e-007, 2.9743137e-007, -6.25863322e-007, -1, 3.63804986e-010))
mesh("SpecialMesh",Part,Enum.MeshType.Wedge,"",Vector3.new(0, 0, 0),Vector3.new(0.285714298, 1, 1))
Part=part(Enum.FormFactor.Brick,m,Enum.Material.SmoothPlastic,0,0,"Black","SwordPart",Vector3.new(1, 1.20000005, 1))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(3.57627869e-007, -0.809324801, 1.96695328e-006, 6.20105922e-008, 2.27451835e-010, -1, 1.81795622e-006, 1, 2.27856845e-010, 1, -1.81795622e-006, 6.2011928e-008))
mesh("SpecialMesh",Part,Enum.MeshType.Head,"",Vector3.new(0, 0, 0),Vector3.new(0.285714298, 0.142857134, 0.285714298))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(0.483492821, 0.539954185, 0.539909601))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(0.00226664543, 0.69951874, 1.00827909, 5.41296288e-007, 9.50464596e-010, -1, 0.707107663, -0.707105815, 3.8208583e-007, -0.707105815, -0.707107663, -3.83435292e-007))
mesh("SpecialMesh",Part,Enum.MeshType.Wedge,"",Vector3.new(0, 0, 0),Vector3.new(1, 0.285714179, 0.285714179))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.SmoothPlastic,0,0,"Black","SwordPart",Vector3.new(0.892679513, 0.539954185, 0.771299422))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-1.19487548, -0.00217807293, 3.74913216e-005, 2.29479338e-006, 1, 7.06279479e-012, -6.20287395e-008, -7.34701189e-012, 1, 1, -2.29479338e-006, 6.20337914e-008))
mesh("CylinderMesh",Part,"","",Vector3.new(0, 0, 0),Vector3.new(1, 0.857145786, 1))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(0.892679513, 0.539954185, 0.771299422))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-1.19487882, -0.00217807293, 4.00543213e-005, 2.0563748e-006, 1, 1.14326326e-011, -6.20178255e-008, -1.28039801e-011, 1, 1, -2.0563748e-006, 6.20228633e-008))
mesh("CylinderMesh",Part,"","",Vector3.new(0, 0, 0),Vector3.new(1.10000002, 0.571431458, 1.10000002))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(0.483492851, 0.539954185, 0.539909601))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-0.00595891476, -1.00750566, 1.00747085, -1.81721958e-007, -3.98678424e-010, 1, -0.707107067, 0.707106411, -1.28216811e-007, -0.707106411, -0.707106948, -1.28784094e-007))
mesh("SpecialMesh",Part,Enum.MeshType.Wedge,"",Vector3.new(0, 0, 0),Vector3.new(1, 0.285714179, 0.285714179))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(0.483492821, 0.539954185, 0.539909601))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(0.00534570217, -1.00757694, -0.698815584, 2.4158129e-007, 4.89748686e-010, -1, -0.707107604, 0.707105875, -1.70486445e-007, 0.707105815, 0.707107544, 1.71177419e-007))
mesh("SpecialMesh",Part,Enum.MeshType.Wedge,"",Vector3.new(0, 0, 0),Vector3.new(1, 0.285714179, 0.285714269))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(0.493492872, 0.539954185, 0.539909601))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-0.000260472298, 0.6988675, -0.698937058, 3.01447898e-007, 5.80818948e-010, -1, -0.707105994, -0.707107365, -2.13563524e-007, -0.707107365, 0.707106113, -2.12752497e-007))
mesh("SpecialMesh",Part,Enum.MeshType.Wedge,"",Vector3.new(0, 0, 0),Vector3.new(1, 0.285714179, 0.285714269))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(1.46267962, 0.200000003, 0.200000003))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-0.00927072763, -0.0121991634, 1.19311547, 0.999999881, -2.08614802e-006, 1.9306286e-007, -1.93059051e-007, -1.09411957e-007, 1, -2.08616257e-006, -0.999999881, -1.09408283e-007))
mesh("BlockMesh",Part,"","",Vector3.new(0, 0, 0),Vector3.new(1, 1, 1))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(1.06267953, 0.200000003, 0.200000003))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-0.604586363, -0.0121991634, 1.02863288, 0.866026282, 0.499998033, 2.28958157e-007, -1.93872992e-007, -1.22099237e-007, 1, 0.499998033, -0.866026282, -8.79730777e-009))
mesh("BlockMesh",Part,"","",Vector3.new(0, 0, 0),Vector3.new(1, 1, 1))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(1.46267962, 0.200000003, 0.200000003))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-1.03790355, -0.0121991634, 0.588528812, 0.500001669, 0.866024196, 1.74744486e-007, -1.6279435e-007, -1.0777579e-007, 1, 0.866024196, -0.500001669, 8.71042545e-008))
mesh("BlockMesh",Part,"","",Vector3.new(0, 0, 0),Vector3.new(1, 1, 1))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(0.662679553, 0.200000003, 0.200000003))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-1.39311564, -0.0121991634, -0.00927072763, 2.08616257e-006, 0.999999881, 7.82298955e-008, -1.51383063e-007, -7.82268899e-008, 1, 0.999999881, -2.08614802e-006, 1.51386175e-007))
mesh("BlockMesh",Part,"","",Vector3.new(0, 0, 0),Vector3.new(1, 1, 1))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(1.46267951, 0.200000003, 0.200000003))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-1.02863288, -0.0121997595, -0.604586482, -0.499998093, 0.866026223, -6.44970513e-008, -1.45620604e-007, -9.60127267e-009, 1, 0.866026223, 0.499998093, 1.30918266e-007))
mesh("BlockMesh",Part,"","",Vector3.new(0, 0, 0),Vector3.new(1, 1, 1))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(1.06267953, 0.200000003, 0.200000003))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-0.588528991, -0.0121992826, -1.03790355, -0.866024137, 0.500001729, -9.11133142e-008, -1.16737233e-007, -1.99774206e-008, 1, 0.500001729, 0.866024137, 7.56750538e-008))
mesh("BlockMesh",Part,"","",Vector3.new(0, 0, 0),Vector3.new(1, 1, 1))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(0.372464359, 0.762464345, 0.762464285))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-0.00338602066, -0.736121356, -0.540583551, 5.41296288e-007, 9.50464596e-010, -1, 0.707107663, -0.707105815, 3.8208583e-007, -0.707105815, -0.707107663, -3.83435292e-007))
mesh("SpecialMesh",Part,Enum.MeshType.Wedge,"",Vector3.new(0, 0, 0),Vector3.new(0.895366609, 0.128561974, 0.128542364))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(0.382464379, 0.762464345, 0.762464285))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(0.00803625584, -0.737174749, 0.736498654, 3.01447898e-007, 5.80818948e-010, -1, -0.707105994, -0.707107365, -2.13563524e-007, -0.707107365, 0.707106113, -2.12752497e-007))
mesh("SpecialMesh",Part,Enum.MeshType.Wedge,"",Vector3.new(0, 0, 0),Vector3.new(0.913885474, 0.128561974, 0.128542408))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(0.40246433, 0.762464345, 0.762464285))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(0.00594449043, 0.540397167, 0.737201214, 2.4158129e-007, 4.89748686e-010, -1, -0.707107604, 0.707105875, -1.70486445e-007, 0.707105815, 0.707107544, 1.71177419e-007))
mesh("SpecialMesh",Part,Enum.MeshType.Wedge,"",Vector3.new(0, 0, 0),Vector3.new(0.895366609, 0.128561974, 0.128542408))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(0.40246433, 0.762464345, 0.762464285))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-0.00681877136, 0.540436149, -0.541088939, -1.81721958e-007, -3.98678424e-010, 1, -0.707107067, 0.707106411, -1.28216811e-007, -0.707106411, -0.707106948, -1.28784094e-007))
mesh("SpecialMesh",Part,Enum.MeshType.Wedge,"",Vector3.new(0, 0, 0),Vector3.new(0.895366669, 0.128561974, 0.128542364))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.SmoothPlastic,0,0,"Black","SwordPart",Vector3.new(1.26045096, 0.762464345, 0.762464285))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(0.910848916, -0.00147974491, 0.000465214252, 2.29479338e-006, 1, 7.06279479e-012, -6.20287395e-008, -7.34701189e-012, 1, 1, -2.29479338e-006, 6.20337914e-008))
mesh("CylinderMesh",Part,"","",Vector3.new(0, 0, 0),Vector3.new(1, 0.385687381, 0.642712057))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.Neon,0,0,"Cyan","SwordPart",Vector3.new(1.26045096, 0.762464345, 0.762464285))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(0.910846829, -0.00147974491, 0.000467300415, 2.0563748e-006, 1, 1.14326326e-011, -6.20178255e-008, -1.28039801e-011, 1, 1, -2.0563748e-006, 6.20228633e-008))
mesh("CylinderMesh",Part,"","",Vector3.new(0, 0, 0),Vector3.new(1.10000002, 0.257125348, 0.706983268))
Part=part(Enum.FormFactor.Custom,m,Enum.Material.SmoothPlastic,0,0,"Black","SwordPart",Vector3.new(0.200000003, 0.200000003, 0.200000003))
Partweld=weld(m,handle,Part,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-3.98755074e-005, -0.86527884, -0.00526940823, 0.99999994, -3.33786011e-006, -1.61662047e-006, 3.33786011e-006, 0.99999994, -1.75251103e-009, 1.61662604e-006, 1.74897963e-009, 1))
mesh("CylinderMesh",Part,"","",Vector3.new(0, 0, 0),Vector3.new(0.857142806, 0.857145548, 0.857142746))
Hitbox=part(Enum.FormFactor.Custom,m,Enum.Material.SmoothPlastic,0,1,"Black","Hitbox",Vector3.new(0.650000036, 4.19999981, 0.200000003))
Hitboxweld=weld(m,handle,Hitbox,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(-0.0107657909, -3.95914412, 0.00325751305, 0.999999821, -0.000211339415, 2.39198562e-006, 0.000211339124, 0.999997795, -6.21902582e-005, -2.38056168e-006, 6.20116552e-005, 0.999992907))
EffectPart=part(Enum.FormFactor.Custom,m,Enum.Material.SmoothPlastic,0,1,"Cyan","EffectPart",Vector3.new(0.200000003, 0.200000003, 0.200000003))
EffectPartweld=weld(m,handle,EffectPart,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(0.00693154335, 0.014090538, 6.03910685, -5.23798153e-005, -6.36925748e-008, -1, 0.99999994, -0.000210702419, -5.23798008e-005, -0.000210702419, -0.99999994, 7.47295417e-008))
mesh("BlockMesh",EffectPart,"","",Vector3.new(0, 0, 0),Vector3.new(1, 1, 1))
EffectPart2=part(Enum.FormFactor.Custom,m,Enum.Material.SmoothPlastic,0,1,"Black","EffectPart2",Vector3.new(0.200000003, 0.200000003, 0.200000003))
EffectPart2weld=weld(m,Character["Left Arm"],EffectPart2,CFrame.new(0, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1),CFrame.new(1.15575993, 0.00814216491, -0.0231294632, -5.23798153e-005, 0.999999821, -0.000210702419, -6.36925748e-008, -0.00021070239, -0.99999994, -1, -5.23797935e-005, 7.47295417e-008))

local ColorsArray = {ColorSequenceKeypoint.new(0, Color3.new(0/255,170/255,255/255)),ColorSequenceKeypoint.new(1, Color3.new(0/255,170/255,255/255))}
local Atch1 = Instance.new("Attachment",Hitbox)Atch1.Position = Vector3.new(0,2,0)
local Atch2 = Instance.new("Attachment",Hitbox)Atch2.Position = Vector3.new(0,-2.5,0)
local Trail = Instance.new("Trail",Hitbox)Trail.Attachment0 = Atch1 Trail.Attachment1 = Atch2
Trail.Texture = "rbxassetid://22636887" Trail.Lifetime = 0.05 Trail.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(1,1,0)})
Trail.Color = ColorSequence.new(ColorsArray) Trail.LightEmission = 1

DarkRiftF=function(par)
while lol == true do 
wait() 
local PWN={}
for _,v in pairs(game.Workspace:children()) do
if v.className=="Model" and v:FindFirstChild("Humanoid")~=nil then
if v.Humanoid.Health>0 and v:FindFirstChild("Torso")~=nil then
table.insert(PWN,v.Torso)
end
end
end
for _,t in pairs(PWN) do
local targ=par.Position-t.Position
local Mag=targ.magnitude
if not t:IsDescendantOf(Character) and t~=nil and Mag<=50 then
if Mag<=30 then
t.Parent.Humanoid:TakeDamage(.5)
local rl=Instance.new("BodyAngularVelocity")
rl.P=3000
rl.maxTorque=Vector3.new(500000,500000,500000)*5000
rl.angularvelocity=Vector3.new(math.random(-20,20),math.random(-20,20),math.random(-20,20))/10
rl.Parent=t
game:GetService("Debris"):AddItem(rl,.1)
end
if Mag<=20 then
t.Parent.Humanoid:TakeDamage(.1)
else
local vl=Instance.new("BodyVelocity")
vl.P=3000
vl.maxForce=Vector3.new(50000000000,50000000000,50000000000)
vl.velocity=(t.Position-par.Position).unit*-(70/(Mag))
vl.Parent=t
game:GetService("Debris"):AddItem(vl,.1)
end
end
end
wait(.08)
end
end

function DerpMagic(part,x1,y1,z1,x2,y2,z2,color) 
	local msh1 = Instance.new("BlockMesh") 
	msh1.Scale = Vector3.new(0.5,0.5,0.5) 
	local S=Instance.new("Part")
	S.Name="Effect"
	S.Material="Neon"
	S.formFactor=0
	S.Size=Vector3.new(x1,y1,z1)
	S.BrickColor=color
	S.Reflectance = 0
	S.TopSurface=0
	S.BottomSurface=0
	S.Transparency=0
	S.Anchored=false
	S.CanCollide=false
	S.CFrame=part.CFrame
	S.Parent=game.Workspace
	msh1.Parent = S
	local W=Instance.new("Weld")
	W.Parent=S
	W.Part0=S
	W.Part1=part
	W.C0=CFrame.new(x2,y2,z2) * CFrame.fromEulerAnglesXYZ(math.random(-50,50),math.random(-50,50),math.random(-50,50))
	W.Parent=nil
	S.Anchored=true
	coroutine.resume(coroutine.create(function(Part,Weld) for i=1, 9 do Part.Mesh.Scale = Part.Mesh.Scale + Vector3.new(0.1,0.1,0.1) --[[Part.CFrame=Part.CFrame*CFrame.fromEulerAnglesXYZ(math.random(-50,50),math.random(-50,50),math.random(-50,50))]] Part.Transparency=i*.1 wait() end Part.Parent=nil Weld.Parent=nil end),S,W)
end 

local function BlackHole(parent,cframe)
local effectsmsh = Instance.new("SpecialMesh")
effectsmsh.MeshId = "http://www.roblox.com/asset/?id=15887356"
--effectsmsh.Scale = Vector3.new(1,1,2.5)
effectsmsh.Scale = Vector3.new(3,3,3)
local effectsg = Instance.new("Part")
effectsg.formFactor = 3
effectsg.CanCollide = false
effectsg.Name = "Effect"
effectsg.Locked = true
effectsg.Transparency = 1 
effectsg.Size = Vector3.new(0.2,0.2,0.2)
effectsg.Parent = parent
effectsg.BrickColor = BrickColor.new("Cyan")
effectsg.Material="Neon"
coroutine.resume(coroutine.create(function(Part,Mesh)
	local Mesh = Instance.new("SpecialMesh") 
	Mesh.Scale = Vector3.new(0.5,0.5,0.5) 
	Mesh.MeshType = "Sphere" 
--	Mesh.TextureId="http://www.roblox.com/asset/?id=1529460"
	Part=Instance.new("Part")
	Part.Name="Effect"
	Part.formFactor=0
	Part.Size=Vector3.new(1,1,1)
	Part.BrickColor=BrickColor.new("Cyan")
	Part.Material="Neon"
	Part.Reflectance = 0
	Part.TopSurface=0
	Part.BottomSurface=0
	Part.Transparency=0
	Part.Anchored=true
NoOutline(Part)	
	Part.CanCollide=false
	Part.CFrame=cframe
	Part.Parent=parent
	Mesh.Parent = Part
	lol=true
coroutine.resume(coroutine.create(function()
	DarkRiftF(Part)
end)) 
	for i=0,200 do
	wait()
	DerpMagic(Part,1,i/3,1,0,i/3,0,BrickColor.new("Cyan")) 
	Mesh.Scale=Mesh.Scale-Vector3.new(0.2,0.2,0.2)
	Part.CFrame=cframe*CFrame.fromEulerAnglesXYZ(math.random(-50,50),math.random(-50,50),math.random(-50,50))
	end
	local fff=200
	for i=0,100 do
	wait()
	DerpMagic(Part,1,fff/3,1,0,fff/3,0,BrickColor.new("Cyan")) 
	Part.CFrame=cframe*CFrame.fromEulerAnglesXYZ(math.random(-50,50),math.random(-50,50),math.random(-50,50))
	end
	for i=0,1,0.05 do
	wait()
	Part.Transparency=Part.Transparency+0.05
	Mesh.Scale=Mesh.Scale+Vector3.new(1.5,1.5,1.5)
	end
	lol=false
	Part.Parent=nil
end),nil,nil)
end

function makeShockwave(height,color,speed,range,pulse)
local range = range or 2000
local p = Instance.new("Part")
p.Anchored = true
p.CanCollide = false
p.FormFactor = "Custom"
p.BrickColor = color
p.Parent = workspace
local m = Instance.new("SpecialMesh",p)
m.MeshId = "rbxassetid://3270017"
local estimateSurvival = math.floor(range/speed) * 0.03
game:GetService("Debris"):AddItem(p,estimateSurvival)
Spawn(function ()
for i = 1,range,speed do
p.Transparency = 1-math.min(0.5,3-(i/500))
m.Scale = Vector3.new(i,i,i*height)
p.CFrame = CFrame.new(Torso.Position) * CFrame.Angles(math.rad(90),0,0)
wait()
end
p:Destroy()
end)
end

function MagicCircle(brickcolor,cframe,x1,y1,z1,x3,y3,z3,delay)
local prt=ppart(3,game.Workspace,0,0,brickcolor,"Effect",vt(0.5,0.5,0.5))
prt.Anchored=true
prt.CFrame=cframe
local msh=mesh("SpecialMesh",prt,"Sphere","",vt(0,0,0),vt(.1,.1,.1))
game:GetService("Debris"):AddItem(prt,2)
coroutine.resume(coroutine.create(function(Part,Mesh) 
for i=0,2,delay do
wait()
Part.CFrame=Part.CFrame
Part.Transparency=i
Mesh.Scale=Mesh.Scale+vt(x3,y3,z3)
end
Part.Parent=nil
end),prt,msh)
end

function MagicBlock(brickcolor,cframe,x1,y1,z1,x3,y3,z3,delay)
local prt=ppart(3,game.Workspace,0,1,brickcolor,"Effect",vt(0.5,0.5,0.5))
prt.Anchored=true
prt.CFrame=cframe
local msh=mesh("BlockMesh",prt,"","",vt(0,0,0),vt(x1,y1,z1))
game:GetService("Debris"):AddItem(prt,5)
coroutine.resume(coroutine.create(function(Part,Mesh) 
for i=0,1,delay do
wait()
Part.CFrame=Part.CFrame*euler(math.random(-50,50),math.random(-50,50),math.random(-50,50))
Part.Transparency=i
Mesh.Scale=Mesh.Scale+vt(x3,y3,z3)
end
Part.Parent=nil
end),prt,msh)
end

local function MagicRing(brickcolor,cframe,x1,y1,z1,x3,y3,z3,delay,Type,parent)
local prt=ppart(3,game.Workspace,0,1,brickcolor,"Effect",vt())
if Type~=2 then
prt.Anchored=true
end
prt.CFrame=cframe
local msh=mesh("SpecialMesh",prt,"FileMesh","http://www.roblox.com/asset/?id=3270017",vt(0,0,0),vt(x1,y1,z1))
game:GetService("Debris"):AddItem(prt,5)
coroutine.resume(coroutine.create(function(Part,Mesh,dur) 
local wld=nil
if dur==2 then
wld=weld(Part,Part,parent,euler(0,0,0)*cf(0,0,0))
end
for i=0,1,delay do
swait()
if dur==1 then
Part.CFrame=Part.CFrame
elseif dur==2 then
wld.C0=cframe
end
Part.Transparency=i
Mesh.Scale=Mesh.Scale+vt(x3,y3,z3)
end
Part.Parent=nil
end),prt,msh,Type)
end

function MagicWaveThing(brickcolor,cframe,x1,y1,z1,x3,y3,z3,delay)
local prt=ppart(3,game.Workspace,0,0,brickcolor,"Effect",vt(0.5,0.5,0.5))
prt.Anchored=true
prt.CFrame=cframe
local msh=mesh("SpecialMesh",prt,"FileMesh","http://www.roblox.com/asset/?id=1051557",vt(0,0,0),vt(x1,y1,z1))
game:GetService("Debris"):AddItem(prt,5)
coroutine.resume(coroutine.create(function(Part,Mesh) 
for i=0,1,delay do
swait()
Part.CFrame=Part.CFrame*euler(0,0.7,0)
Part.Transparency=i
Mesh.Scale=Mesh.Scale+vt(x3,y3,z3)
end
Part.Parent=nil
end),prt,msh)
end

function MagicCylinder(brickcolor,cframe,x1,y1,z1,x3,y3,z3,delay)
local prt=ppart(3,workspace,0,0,brickcolor,"Effect",vt(0.2,0.2,0.2))
prt.Anchored=true
prt.CFrame=cframe
local msh=mesh("SpecialMesh",prt,"Head","",vt(0,0,0),vt(x1,y1,z1))
game:GetService("Debris"):AddItem(prt,5)
coroutine.resume(coroutine.create(function(Part,Mesh) 
for i=0,1,delay do
wait()
Part.CFrame=Part.CFrame
Part.Transparency=i
Mesh.Scale=Mesh.Scale+vt(x3,y3,z3)
end
Part.Parent=nil
end),prt,msh)
end 

function MagicWave(brickcolor,cframe,x1,y1,z1,x3,y3,z3,delay)
local prt=ppart(3,workspace,0,0,brickcolor,"Effect",vt())
prt.Anchored=true
prt.CFrame=cframe
local msh=mesh("SpecialMesh",prt,"FileMesh","http://www.roblox.com/asset/?id=20329976",vt(0,0,0),vt(x1,y1,z1))
game:GetService("Debris"):AddItem(prt,5)
table.insert(Effects,{prt,"Cylinder",delay,x3,y3,z3})
end

function Blast(parent)
MagicBlock(BrickColor.new("Black"),parent.CFrame,4,4,4,0.2,0.2,0.2,0.01)
MagicWaveThing(BrickColor.new("Black"),parent.CFrame,4,4,4,0.2,0.2,0.2,0.01)
end

function ChargeBall(parent,t)
local counter=0
local size=1
for i=0,t,1 do
swait()
counter=counter+1
if counter%10==0 then
if size==3 then
MagicRing(BrickColor.new("Black"),parent.CFrame,.5,.5,.5,1,1,1,0.1,3,parent)
elseif size==2 then
MagicRing(BrickColor.new("Black"),parent.CFrame,.5,.5,.5,1,1,1,0.1,3,parent)
end
end
if counter%5==0 then
if size==1 then
MagicBlock(BrickColor.new("Black"),parent.CFrame,.5,.5,.5,1,1,1,0.1,3,parent)
elseif size==2 then
MagicBlock(BrickColor.new("Black"),parent.CFrame,.5,.5,.5,1,1,1,0.1,3,parent)
elseif size==3 then
MagicBlock(BrickColor.new("Black"),parent.CFrame,.5,.5,.5,1,1,1,0.1,3,parent)
end
end
end
end

function ChargeBall2(parent,t)
local counter=0
local size=1
for i=0,t,1 do
swait()
counter=counter+1
if counter%10==0 then
if size==3 then
MagicRing(BrickColor.new("Black"),parent.CFrame,.5,.5,.5,1,1,1,0.1,3,parent)
elseif size==2 then
MagicRing(BrickColor.new("Black"),parent.CFrame,.5,.5,.5,1,1,1,0.1,3,parent)
end
end
if counter%5==0 then
if size==1 then
MagicBlock(BrickColor.new("Black"),parent.CFrame,.5,.5,.5,1,1,1,0.1,3,parent)
MagicWave(BrickColor.new("Cyan"),cf(Torso.Position)*cf(0,-1,0)*euler(0,math.random(-50,50),0),1,1,1,1,.5,1,0.05)
elseif size==2 then
MagicBlock(BrickColor.new("Black"),parent.CFrame,.5,.5,.5,1,1,1,0.1,3,parent)
MagicWave(BrickColor.new("Cyan"),cf(Torso.Position)*cf(0,-1,0)*euler(0,math.random(-50,50),0),1,1,1,1,.5,1,0.05)
elseif size==3 then
MagicBlock(BrickColor.new("Black"),parent.CFrame,.5,.5,.5,1,1,1,0.1,3,parent)
MagicWave(BrickColor.new("Cyan"),cf(Torso.Position)*cf(0,-1,0)*euler(0,math.random(-50,50),0),1,1,1,1,.5,1,0.05)
end
end
end
end

function MagniDamage(Part,dis,mind,maxd,force,knock)
for _,c in pairs(workspace:children()) do
local hum=c:findFirstChild("Humanoid")
if hum~=nil then
local head=c:findFirstChild("Torso")
if head~=nil then
local targ=head.Position-Part.Position
local mag=targ.magnitude
if mag<=dis and c.Name~=Character.Name then 
Damagefunc(Part,hum.Parent.Torso,mind,maxd,force,knock,RootPart,.2,1)
end
end
end
end
end

function computeDirection(vec)
local lenSquared = vec.magnitude * vec.magnitude
local invSqrt = 1 / math.sqrt(lenSquared)
return Vector3.new(vec.x * invSqrt, vec.y * invSqrt, vec.z * invSqrt)
end

function attackone()
attack = true
local hitsounds={"199149137","199149186","199149221","199149235","199149269","199149297"}
local con=Hitbox.Touched:connect(function(hit) Damagefunc(Hitbox,hit,5,9,math.random(5,5),"Normal",RootPart,.2,1) end) 
local fx=Hitbox.Touched:connect(function(part)
	local human=part.Parent:findFirstChild("Humanoid")
	if human~=nil and bounce==false then
		bounce=true
		local rndm=math.random(1,#hitsounds)
		local r=rndm
		so("http://www.roblox.com/asset/?id="..hitsounds[r],part.Parent,1,1)
	end
end)
for i = 0,1,0.25 do
swait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(-90)),1)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(0),math.rad(0),math.rad(50)),1)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(0), math.rad(10), math.rad(100)),1)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-60)),1)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(120),math.rad(0)),1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(0),math.rad(0)),1)
end
so("http://www.roblox.com/asset/?id=712781677",handle,1,.9)
for i = 0,1,0.5 do
swait()
local blcf = Hitbox.CFrame*CFrame.new(0,.5,0)
if scfr and (Hitbox.Position-scfr.p).magnitude > .1 then
local h = 5
scfr = blcf
elseif not scfr then
scfr = blcf
end
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(80)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(10),math.rad(-10),math.rad(-80)),0.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(0), math.rad(120), math.rad(90)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-30)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(50),math.rad(0)),0.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(-25),math.rad(0),math.rad(0)),.5)
end
attack = false
bounce=false
scfr=nil
fx:disconnect()
con:disconnect()
end

function attacktwo()
attack=true
local hitsounds={"199149137","199149186","199149221","199149235","199149269","199149297"}
local con=Hitbox.Touched:connect(function(hit) Damagefunc(Hitbox,hit,4,9,math.random(5,5),"Normal",RootPart,.2,1) end)
local fx=Hitbox.Touched:connect(function(part)
	local human=part.Parent:findFirstChild("Humanoid")
	if human~=nil and bounce==false then
		bounce=true
		local rndm=math.random(1,#hitsounds)
		local r=rndm
		so("http://www.roblox.com/asset/?id="..hitsounds[r],part.Parent,1,1)
	end
end)
for i=0,1,.25 do
swait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(90)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(10),math.rad(-10),math.rad(-90)),0.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(0), math.rad(120), math.rad(90)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-30)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(40),math.rad(0)),0.4)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-140),math.rad(-10)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(-25),math.rad(0),math.rad(0)),.5)
end
so("http://www.roblox.com/asset/?id=712781677",handle,1,1)
for i = 0,1,0.5 do
swait()
local blcf = Hitbox.CFrame*CFrame.new(0,.5,0)
if scfr and (Hitbox.Position-scfr.p).magnitude > .1 then
local h = 5
scfr = blcf
elseif not scfr then
scfr = blcf
end
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(-90)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(10),math.rad(0),math.rad(90)),0.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(0), math.rad(10), math.rad(90)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-90)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(140),math.rad(0)),0.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-40),math.rad(-10)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.5)
end
scfr=nil
attack=false
bounce=false
con:disconnect()
fx:disconnect()
end

function attackthree()
attack=true
local hitsounds={"199149137","199149186","199149221","199149235","199149269","199149297"}
local con=Hitbox.Touched:connect(function(hit) Damagefunc(Hitbox,hit,12,16,math.random(5,5),"Normal",RootPart,.2,1) end) 
local fx=Hitbox.Touched:connect(function(part)
	local human=part.Parent:findFirstChild("Humanoid")
	if human~=nil and bounce==false then
		bounce=true
		local rndm=math.random(1,#hitsounds)
		local r=rndm
		so("http://www.roblox.com/asset/?id="..hitsounds[r],part.Parent,1,1)
	end
end)
for i=0,1,.25 do
swait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(-30)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(0),math.rad(0),math.rad(30)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(170), math.rad(0), math.rad(20)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(25), math.rad(0), math.rad(-30)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(105),math.rad(0)),0.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-75),math.rad(-10)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.5)
end
so("http://www.roblox.com/asset/?id=712781677",handle,1,.9)
for i = 0,1,0.5 do
swait()
local blcf = Hitbox.CFrame*CFrame.new(0,.5,0)
if scfr and (Hitbox.Position-scfr.p).magnitude > .1 then
local h = 5
scfr = blcf
elseif not scfr then
scfr = blcf
end
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(50)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(10),math.rad(0),math.rad(-50)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(20), math.rad(0), math.rad(-10)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-10)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(80),math.rad(0)),0.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-100),math.rad(-10)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(-40),math.rad(0),math.rad(0)),.5)
end
attack=false
bounce=false
scfr=nil
con:disconnect()
fx:disconnect()
end

function attackfour()
attack = true
local hitsounds={"199149137","199149186","199149221","199149235","199149269","199149297"}
local con=Hitbox.Touched:connect(function(hit) Damagefunc(Hitbox,hit,4,9,math.random(20,30),"Normal",RootPart,.2,1) end)
local fx=Hitbox.Touched:connect(function(part)
	local human=part.Parent:findFirstChild("Humanoid")
	if human~=nil and bounce==false then
		bounce=true
		local rndm=math.random(1,#hitsounds)
		local r=rndm
		so("http://www.roblox.com/asset/?id="..hitsounds[r],part.Parent,1,1)
	end
end)
for i = 0,1,0.25 do
swait()
RootJoint.C0=clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(10),math.rad(-5),math.rad(-60)),.5)
Torso.Neck.C0=clerp(Torso.Neck.C0,necko *angles(math.rad(-10),math.rad(0),math.rad(60)),.5)
RW.C0=clerp(RW.C0,cf(1.5, 0.8, 0.2) * angles(math.rad(5), math.rad(-15), math.rad(112)), 0.5)
LW.C0=clerp(LW.C0,cf(-1.5, 0.5, 0) * angles(math.rad(30), math.rad(0), math.rad(-20)), 0.5)
RH.C0=clerp(RH.C0,cf(1.1,-1,0)*angles(math.rad(-5),math.rad(120),math.rad(-8)),.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(5),math.rad(-60),math.rad(0)),.5)
handleweld.C0=clerp(handleweld.C0,cf(0,-.2,.5)*angles(math.rad(50),math.rad(-15),math.rad(0)),.5)
end
so("http://www.roblox.com/asset/?id=712781677",Hitbox,1,1.1)
local v=it("BodyVelocity",Torso)
v.maxForce=Vector3.new(4e+005,4e+005,4e+005)*1
v.velocity=RootPart.CFrame.lookVector*50
for i = 0,1,0.5 do
swait()
local blcf = Hitbox.CFrame*cf(0,0,0)
if scfr and (Hitbox.Position-scfr.p).magnitude > .1 then
local h = 5
scfr = blcf
elseif not scfr then
scfr = blcf
end
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(5),math.rad(60)),.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(0),math.rad(0),math.rad(-60)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(-10), math.rad(60), math.rad(100)), 0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(-30), math.rad(0), math.rad(-15)), 0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(0)),.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(0)),.5)
handleweld.C0=clerp(handleweld.C0,cf(0,-1,-1)*angles(math.rad(-100),math.rad(0),math.rad(0)),.5)
end
v.Parent=nil
scfr=nil
attack = false
bounce=false
con:disconnect()
fx:disconnect()
end

function Shockwave1(CFramez, Rangez)
local Shock = Instance.new("Part",game.Workspace)Shock.Transparency = 0.75 Shock.Size = Vector3.new(0.2,0.2,0.2) Shock.Anchored = true
Shock.CanCollide = false Shock.BrickColor = BrickColor.new("Medium stone grey") local SM = Instance.new("SpecialMesh",Shock)
SM.MeshId = "rbxassetid://20329976" Shock.CFrame = CFramez SM.Scale = Vector3.new(0,0,0)
Spawn(function ()
for i = 1,3 do
SM.Scale = SM.Scale + Vector3.new(2+Rangez/2,0.15+Rangez/12,2+Rangez/2)
Shock.CFrame = Shock.CFrame* CFrame.new(0,0,0)*CFrame.Angles(0,math.rad(-80/Rangez),0)
wait()
end
for i = 1,math.huge do
if Shock.Transparency >= 1 then break end
Shock.Transparency = Shock.Transparency + 0.025 Shock.CFrame = Shock.CFrame* CFrame.new(0,0,0)*CFrame.Angles(0,math.rad(-150/Rangez),0)
SM.Scale = SM.Scale + Vector3.new(0.5,0.05,0.5)
wait()
end
Shock:remove()
end)
end


function PortalStorm()
attack=true
local hitsounds={"199149137","199149186","199149221","199149235","199149269","199149297"}
so("http://www.roblox.com/asset/?id=562500427",handle,1,.9)
MagniDamage(Character.HumanoidRootPart,20,150,235,0,"Normal",Character.HumanoidRootPart)
local BV = Instance.new("BodyVelocity",Character.HumanoidRootPart)BV.Velocity = Vector3.new(0,1,0)game.Debris:AddItem(BV,0.1)
BV.maxForce = Vector3.new(0,math.huge,0)
for i2 = 1,10 do
Shockwave1(Character.HumanoidRootPart.CFrame*CFrame.new(0,-2.5,0)*CFrame.Angles(0,math.rad(-5),0), i2)
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(-(i2*100))),1)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(0),math.rad(0),math.rad(125)),1)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(0), math.rad(10), math.rad(100)),1)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-60)),1)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(120),math.rad(0)),1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(0),math.rad(0)),1)
swait()
end
attack = false
bounce=false
scfr=nil
attack = false
end

function Spin()
attack=true
local hitsounds={"199149137","199149186","199149221","199149235","199149269","199149297"}
so("http://www.roblox.com/asset/?id=562500427",handle,1,.9)
local BV = Instance.new("BodyVelocity",Character.HumanoidRootPart)BV.Velocity = Vector3.new(0,50,0)game.Debris:AddItem(BV,0.25)
BV.maxForce = Vector3.new(0,math.huge,0)
for i2 = 1,25 do
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(math.random(-100,100)/10),math.rad(math.random(-100,100)/10),math.rad(-(i2*50))),1)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(0),math.rad(0),math.rad(125)),1)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(0), math.rad(10), math.rad(100)),1)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-60)),1)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(120),math.rad(0)),1)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(0),math.rad(0)),1)
MagniDamage(Character.HumanoidRootPart,10,8,16,0,"Normal",Character.HumanoidRootPart)
swait()
end
attack = false
bounce=false
scfr=nil
attack = false
end

function ProjectileStrike()
attack=true
for i=0,1,.25 do
swait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(-30)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(0),math.rad(0),math.rad(30)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(170), math.rad(0), math.rad(20)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(25), math.rad(0), math.rad(-30)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(105),math.rad(0)),0.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-75),math.rad(-10)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.5)
end
Wave=part(Enum.FormFactor.Custom,m,Enum.Material.SmoothPlastic,0,1,"Black","Wave",Vector3.new(0.650000036, 8, 0.200000003)) Wave.Parent = game.Workspace
local Atch3 = Instance.new("Attachment",Wave)Atch3.Position = Vector3.new(0,4,0)
local Atch4 = Instance.new("Attachment",Wave)Atch4.Position = Vector3.new(0,-4,0)
local Trail2 = Instance.new("Trail",Wave)Trail2.Attachment0 = Atch3 Trail2.Attachment1 = Atch4
Trail2.Texture = "rbxassetid://22636887" Trail2.Lifetime = 0.05 Trail2.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(1,1,0)})
Trail2.Color = ColorSequence.new(ColorsArray) Trail2.LightEmission = 1
Wave.CFrame = Character.HumanoidRootPart.CFrame*CFrame.new(0,0,-1)*CFrame.Angles(0,0,math.rad(math.random(-20,20)))
local BV = Instance.new("BodyVelocity",Wave)BV.maxForce = Vector3.new(math.huge,math.huge,math.huge)BV.velocity = Character.HumanoidRootPart.CFrame.lookVector*250
so("http://www.roblox.com/asset/?id=506383970",handle,1,.9)
local con=Wave.Touched:connect(function(hit) Damagefunc(Wave,hit,24,46,0,"Normal",RootPart,.2,1) end) 
for i = 0,1,0.1 do
swait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(50)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(10),math.rad(0),math.rad(-50)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(math.random(-20,20)), math.rad(0), math.rad(-10)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-10)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(80),math.rad(0)),0.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-100),math.rad(-10)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(-40),math.rad(0),math.rad(0)),.5)
end
attack=false
bounce=false
scfr=nil
con:disconnect()
end

function WorldBreaker()
attack=true
for i=0,1,.25 do
swait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(-30)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(0),math.rad(0),math.rad(30)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(170), math.rad(0), math.rad(20)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(25), math.rad(0), math.rad(-30)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(105),math.rad(0)),0.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-75),math.rad(-10)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.5)
end
Wave=part(Enum.FormFactor.Custom,m,Enum.Material.SmoothPlastic,0,1,"Black","Wave",Vector3.new(6, 100, 20)) Wave.Parent = game.Workspace
local Atch3 = Instance.new("Attachment",Wave)Atch3.Position = Vector3.new(0,50,-10)
local Atch4 = Instance.new("Attachment",Wave)Atch4.Position = Vector3.new(0,-50,-10)
local Trail2 = Instance.new("Trail",Wave)Trail2.Attachment0 = Atch3 Trail2.Attachment1 = Atch4 Trail2.MinLength = 4
Trail2.Texture = "rbxassetid://22636887" Trail2.Lifetime = 5 Trail2.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(1,1,0)})
Trail2.Color = ColorSequence.new(ColorsArray) Trail2.LightEmission = 1
local Soond = SH:clone()Soond.SoundId = "rbxassetid://666736107" Soond.Volume = 3 Soond.Looped = true Soond.Parent = Wave Soond:Play()
Wave.CFrame = Character.HumanoidRootPart.CFrame*CFrame.Angles(0,0,math.rad(-90))*CFrame.new(0,0,-10)
game.Debris:AddItem(Wave,5)
local BV = Instance.new("BodyVelocity",Wave)BV.maxForce = Vector3.new(math.huge,math.huge,math.huge)BV.velocity = Character.HumanoidRootPart.CFrame.lookVector*25
Wave.Touched:connect(function(hit) 
if hit.Anchored == false and hit.Parent ~= Character and hit.Parent.Parent ~= Character then
hit:remove()
end
end) 
so("http://www.roblox.com/asset/?id=517249876",handle,1,.9)
for i = 0,1,0.1 do
swait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(50)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(10),math.rad(0),math.rad(-50)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(math.random(-20,20)), math.rad(0), math.rad(-10)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-10)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(80),math.rad(0)),0.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-100),math.rad(-10)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(-40),math.rad(0),math.rad(0)),.5)
end
attack=false
bounce=false
scfr=nil
end

function SuperProjectile()
attack=true
for i=0,1,.25 do
swait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(-30)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(0),math.rad(0),math.rad(30)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(170), math.rad(0), math.rad(20)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(25), math.rad(0), math.rad(-30)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(105),math.rad(0)),0.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-75),math.rad(-10)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.5)
end
for i2 = 1,3 do
for i = 1,12 do
Wave=part(Enum.FormFactor.Custom,m,Enum.Material.SmoothPlastic,0,1,"Black","Wave",Vector3.new(0.650000036, 10, 10*i2)) Wave.Parent = game.Workspace
game.Debris:AddItem(Wave,10)
local Atch3 = Instance.new("Attachment",Wave)Atch3.Position = Vector3.new(0,10,0)
local Atch4 = Instance.new("Attachment",Wave)Atch4.Position = Vector3.new(0,-10,0)
local Trail2 = Instance.new("Trail",Wave)Trail2.Attachment0 = Atch3 Trail2.Attachment1 = Atch4 Trail2.MinLength = 4
Trail2.Texture = "rbxassetid://22636887" Trail2.Lifetime = 0.5 Trail2.Transparency = NumberSequence.new({NumberSequenceKeypoint.new(0,0,0),NumberSequenceKeypoint.new(1,1,0)})
Trail2.Color = ColorSequence.new(ColorsArray) Trail2.LightEmission = 1
local Soond = SH:clone()Soond.SoundId = "rbxassetid://666736107" Soond.Volume = 0.05 Soond.Looped = true Soond.Parent = Wave Soond:Play()
Wave.CFrame = Character.HumanoidRootPart.CFrame*CFrame.Angles(0,0,math.rad(30*i))
Wave.CFrame = Wave.CFrame*CFrame.new(-5*i2,0,4*i2)
local BV = Instance.new("BodyVelocity",Wave)BV.maxForce = Vector3.new(math.huge,math.huge,math.huge)BV.velocity = Character.HumanoidRootPart.CFrame.lookVector*300
Wave.Touched:connect(function(hit) 
if hit.Anchored == false and hit.Parent ~= Character and hit.Parent.Parent ~= Character then
hit:remove()
end
end) 
end
end
so("http://www.roblox.com/asset/?id=517249876",handle,1,.9)
for i = 0,1,0.1 do
swait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(50)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(10),math.rad(0),math.rad(-50)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(math.random(-20,20)), math.rad(0), math.rad(-10)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-10)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(80),math.rad(0)),0.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-100),math.rad(-10)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(-40),math.rad(0),math.rad(0)),.5)
end
attack=false
bounce=false
scfr=nil
end


function ShockSpin(Partz,SM)
Spawn(function()
for i = 1,math.huge do
if Partz.Transparency >= 1 then break end
Partz.Transparency = Partz.Transparency + 0.025 Partz.CFrame = Partz.CFrame* CFrame.new(0,0,0)*CFrame.Angles(0,math.rad(-50),0)
SM.Scale = SM.Scale + Vector3.new(1,0.25,1)
wait()
end
Partz:remove()
end)
end

function Shockwave2(Partz)
local W = 0
Spawn(function()
for i = 1,math.huge do
W = W + 1
local Shock = Instance.new("Part",game.Workspace)Shock.Transparency = 0.75 Shock.Size = Vector3.new(0.2,0.2,0.2) Shock.Anchored = true
Shock.CanCollide = false Shock.BrickColor = BrickColor.new("Medium stone grey") local SM = Instance.new("SpecialMesh",Shock)
SM.MeshId = "rbxassetid://20329976" Shock.CFrame = Partz.CFrame*CFrame.Angles(math.rad(90),math.rad(W*10),0) SM.Scale = Vector3.new(0,0,0)
ShockSpin(Shock,SM)
wait()
end
end)
end

function SuperProjectile2()
attack=true
for i=0,1,.25 do
swait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(-30)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(0),math.rad(0),math.rad(30)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(170), math.rad(0), math.rad(20)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(25), math.rad(0), math.rad(-30)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(105),math.rad(0)),0.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-75),math.rad(-10)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.5)
end
local Wave2 = Instance.new("Part",game.Workspace)Wave2.Size = Vector3.new(20,20,20)Wave2.CanCollide = false Wave2.Anchored = false Wave2.Transparency = 1
local Soond = SH:clone()Soond.SoundId = "rbxassetid://666736107" Soond.Volume = 0.05 Soond.Looped = true Soond.Parent = Wave2 Soond:Play() Wave2.CFrame = Character.HumanoidRootPart.CFrame
local BV = Instance.new("BodyVelocity",Wave2)BV.maxForce = Vector3.new(math.huge,math.huge,math.huge)BV.velocity = Character.HumanoidRootPart.CFrame.lookVector*150
Wave2.Touched:connect(function(hit) Damagefunc(Wave2,hit,24,46,0,"Normal",RootPart,.2,1) end) 
Shockwave2(Wave2) game.Debris:addItem(Wave2,5)
so("http://www.roblox.com/asset/?id=517249876",handle,1,.9)
for i = 0,1,0.1 do
swait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(50)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(10),math.rad(0),math.rad(-50)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(math.random(-20,20)), math.rad(0), math.rad(-10)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-10)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(80),math.rad(0)),0.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-100),math.rad(-10)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(-40),math.rad(0),math.rad(0)),.5)
end
attack=false
bounce=false
scfr=nil
end

function Warp()
for i=0,1,.25 do
swait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(-30)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(0),math.rad(0),math.rad(30)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(170), math.rad(0), math.rad(20)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(25), math.rad(0), math.rad(-30)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(105),math.rad(0)),0.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-75),math.rad(-10)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.5)
end
local WarpS = m:clone() WarpS:FindFirstChild("MagicWeld"):remove() WarpS.Name = "WarpSword"
WarpS.Parent = Character local Partzs = Instance.new("Part",WarpS)Partzs.Size = Vector3.new(0.2,0.2,0.2)Partzs.CanCollide = false Partzs.Anchored = false Partzs.Transparency = 1
local WeldS = Instance.new("Weld",WarpS.Hitbox)WeldS.Part0 = WarpS.Hitbox WeldS.Part1 = Partzs 
Partzs.CFrame = CFrame.new(Character.HumanoidRootPart.CFrame:toWorldSpace(CFrame.new(0,0,0)).p,mouse.hit.p)
local BV = Instance.new("BodyVelocity",Partzs)BV.maxForce = Vector3.new(math.huge,math.huge,math.huge)BV.velocity = Partzs.CFrame.lookVector*750
Partzs.CFrame = Partzs.CFrame*CFrame.Angles(math.rad(90),math.rad(90),0)
local Soond = SH:clone()Soond.SoundId = "rbxassetid://181004943" Soond.Volume = 10 Soond.Parent = Partzs Soond.PlaybackSpeed = 3 Soond:Play()
local SE = Instance.new("PitchShiftSoundEffect",Soond)SE.Octave = 0.5
Trail.Enabled = false
for i, v in pairs(m:children()) do
if v.ClassName == "Part" then
if v.Transparency ~= 1 then
v.Transparency = 0.99
end
end
end
for i = 0,1,0.1 do
swait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(50)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(10),math.rad(0),math.rad(-50)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(math.random(-20,20)), math.rad(0), math.rad(-10)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-10)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(80),math.rad(0)),0.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-100),math.rad(-10)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(-40),math.rad(0),math.rad(0)),.5)
end
wait(0.05)
local Soond2 = SH:clone()Soond2.SoundId = "rbxassetid://181004957" Soond2.Volume = 5 Soond2.Parent = Character.HumanoidRootPart Soond2:Play()
Character.HumanoidRootPart.CFrame = Partzs.CFrame
Humanoid.Jump = true
WarpS:remove()
Trail.Enabled = true
for i, v in pairs(m:children()) do
if v.ClassName == "Part" then
if v.Transparency ~= 1 then
v.Transparency = 0
end
end
end
end

function NukeShockwaves(Size, CFramez)
local Shock = Instance.new("Part",game.Workspace)Shock.Transparency = 0.5 Shock.Size = Vector3.new(0.2,0.2,0.2) Shock.Anchored = true
Shock.CanCollide = false Shock.BrickColor = BrickColor.new("Medium stone grey") local SM = Instance.new("SpecialMesh",Shock)
SM.MeshId = "rbxassetid://20329976" SM.Scale = Vector3.new(Size,5,Size) Shock.CFrame = CFramez*CFrame.new(0,1,0)*CFrame.Angles(0,math.rad(math.random(-360,360)),0)
Spawn(function()
for i = 1,math.huge do
if Shock.Transparency >= 1 then break end
Shock.Transparency = Shock.Transparency + 0.025
wait()
end
end)
end

function NukeBlade()
for i=0,1,.25 do
swait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(-30)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(0),math.rad(0),math.rad(30)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(170), math.rad(0), math.rad(20)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(25), math.rad(0), math.rad(-30)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(105),math.rad(0)),0.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-75),math.rad(-10)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.5)
end
local WarpS = m:clone() WarpS:FindFirstChild("MagicWeld"):remove() WarpS.Name = "WarpSword"
WarpS.Parent = Character local Partzs = Instance.new("Part",WarpS)Partzs.Size = Vector3.new(0.2,0.2,0.2)Partzs.CanCollide = false Partzs.Anchored = false Partzs.Transparency = 1
local WeldS = Instance.new("Weld",WarpS.Hitbox)WeldS.Part0 = WarpS.Hitbox WeldS.Part1 = Partzs 
Partzs.CFrame = CFrame.new(Character.HumanoidRootPart.CFrame:toWorldSpace(CFrame.new(0,0,0)).p,mouse.hit.p)
local BV = Instance.new("BodyVelocity",Partzs)BV.maxForce = Vector3.new(math.huge,math.huge,math.huge)BV.velocity = Partzs.CFrame.lookVector*750
Partzs.CFrame = Partzs.CFrame*CFrame.Angles(math.rad(90),math.rad(90),0)
local Soond = SH:clone()Soond.SoundId = "rbxassetid://181004943" Soond.Volume = 10 Soond.Parent = Partzs Soond.PlaybackSpeed = 2 Soond:Play()
local SE = Instance.new("PitchShiftSoundEffect",Soond)SE.Octave = 0.5
Trail.Enabled = false
for i, v in pairs(m:children()) do
if v.ClassName == "Part" then
if v.Transparency ~= 1 then
v.Transparency = 0.99
end
end
end
wait(0.02)
local Hit = false
Partzs.Touched:connect(function(Hit)
if Hit == true then return end
Hit = true
Partzs.Anchored = true
local Shock = Instance.new("Part",game.Workspace)Shock.Transparency = 0 Shock.Size = Vector3.new(1,1,1) Shock.Anchored = true
Shock.CanCollide = false Shock.BrickColor = BrickColor.new("Cyan") Shock.Material = "Neon" local SM = Instance.new("SpecialMesh",Shock)
Shock.CFrame = CFrame.new(Partzs.Position) SM.MeshType = "Sphere"
local Pos = Shock.Position
for i = 1,3 do
local Sound = SH:clone()Sound.SoundId = "rbxassetid://258057783" Sound.Volume = 10 Sound.Parent = Shock Sound.PlaybackSpeed = 0.4 Sound:Play()
end
for i = 1,200 do
SM.Scale = SM.Scale + Vector3.new(i*0.025,i*0.025,i*0.025)
NukeShockwaves(i*1.5,CFrame.new(Shock.Position))
MagniDamage(Shock,i*1,10,30,0,"Normal",Character.HumanoidRootPart)
wait()
end
for i = 1,30 do
Shock.Transparency = Shock.Transparency + 1/30
SM.Scale = SM.Scale + Vector3.new(i*0.0,i*0.025,i*0.025)
wait()
end
end)
game.Debris:AddItem(WarpS,10)
for i = 0,1,0.1 do
swait()
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(0),math.rad(0),math.rad(50)),0.5)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(10),math.rad(0),math.rad(-50)),.5)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(math.random(-20,20)), math.rad(0), math.rad(-10)),0.5)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(0), math.rad(0), math.rad(-10)),0.5)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(80),math.rad(0)),0.5)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-100),math.rad(-10)),0.5)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(-40),math.rad(0),math.rad(0)),.5)
end
wait(0.05)
Trail.Enabled = true
for i, v in pairs(m:children()) do
if v.ClassName == "Part" then
if v.Transparency ~= 1 then
v.Transparency = 0
end
end
end
end

attacktype=1
mouse.Button1Down:connect(function()
if attacktype==1 and attack==false then
attacktype=2
attackone()
elseif attacktype==2 and attack==false then
attacktype=3
attacktwo()
elseif attacktype==3 and attack==false then
attacktype=4
attackthree()
elseif attacktype==4 and attack==false then
attacktype=1
attackfour()
end
end)

mouse.KeyDown:connect(function(k)
k=k:lower()
if attack == false and k == 'e' then
Spin()
end
if attack == false and k == 'q' then
ProjectileStrike()
end
if attack == false and k == 'z' then
SuperProjectile()
end
if attack == false and k == 'x' then
SuperProjectile2()
end
if attack == false and k == 'c' then
NukeBlade()
end
if attack == false and k == 'v' then
Warp()
end
if attack == false and k == 'f'then
WorldBreaker()
end
if attack == false and k == 'r'then
PortalStorm()
end
end)


local sine = 0
local change = 1
local val = 0

while true do
swait()
for i, v in pairs(m:children()) do
if v.ClassName == "Part" then
v.Anchored = false
v.CanCollide = false
end
end
for i,v in pairs (Character:children()) do
if v.ClassName == "Part" then
v.Anchored = false
end
if v.ClassName == "Accessory" then
for i,v2 in pairs (v:children()) do
if v2.ClassName == "Part" then
v2.Anchored = false
end
end
end
end
sine = sine + change
local torvel=(RootPart.Velocity*Vector3.new(1,0,1)).magnitude 
local velderp=RootPart.Velocity.y
hitfloor,posfloor=rayCast(RootPart.Position,(CFrame.new(RootPart.Position,RootPart.Position - Vector3.new(0,1,0))).lookVector,4,Character)
if equipped==true or equipped==false then
if attack==false then
idle=idle+1
else
idle=0
end
if idle>=500 then
if attack==false then
end
end
if RootPart.Velocity.y > 1 and hitfloor==nil then 
Anim="Jump"
if attack==false then
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(-5),math.rad(0),math.rad(0)),.3)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(-10),math.rad(0),math.rad(0)),.3)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(-10), math.rad(0), math.rad(15)), 0.3)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(-10), math.rad(0), math.rad(-15)), 0.3)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(-30),math.rad(90),math.rad(20))*angles(math.rad(-5),math.rad(0),math.rad(0)),.3)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(-30),math.rad(-90),math.rad(-20))*angles(math.rad(-5),math.rad(0),math.rad(0)),.3)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(0),math.rad(0),math.rad(0)),.3)
end
elseif RootPart.Velocity.y < -1 and hitfloor==nil then 
Anim="Fall"
if attack==false then
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(10),math.rad(0),math.rad(0)),.3)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(13),math.rad(0),math.rad(0)),.3)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(10), math.rad(0), math.rad(20)), 0.3)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(10), math.rad(0), math.rad(-20)), 0.3)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(0),math.rad(90),math.rad(20))*angles(math.rad(-5),math.rad(0),math.rad(0)),.3)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(0),math.rad(-90),math.rad(-20))*angles(math.rad(-5),math.rad(0),math.rad(0)),.3)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(-15),math.rad(0),math.rad(0)),.3)
end
elseif torvel<1 and hitfloor~=nil then
Anim="Idle"
if attack==false then
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(-2),math.rad(0),math.rad(15)),.3)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(2),math.rad(0),math.rad(-15)),.3)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(15), math.rad(0), math.rad(0)), 0.3)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(-10), math.rad(0), math.rad(0)), 0.3)
RH.C0=clerp(RH.C0,cf(1,-1,0)*angles(math.rad(-2),math.rad(85),math.rad(0)),.3)
LH.C0=clerp(LH.C0,cf(-1,-1,0)*angles(math.rad(-4),math.rad(-95),math.rad(0)),.3)
handleweld.C0=clerp(handleweld.C0,cf(0,0,0)*angles(math.rad(-10),math.rad(-2),math.rad(0)),.2)
end
elseif torvel>2 and hitfloor~=nil then
Anim="Walk"
if attack==false then
change=3
RootJoint.C0 = clerp(RootJoint.C0,RootCF*cf(0,0,0)* angles(math.rad(10),math.rad(0),math.rad(-20)),.3)
Torso.Neck.C0 = clerp(Torso.Neck.C0,necko *angles(math.rad(-10),math.rad(-5),math.rad(25)),.3)
RW.C0 = clerp(RW.C0, CFrame.new(1.5, 0.5, 0) * angles(math.rad(-30), math.rad(-25), math.rad(5)), 0.3)
LW.C0 = clerp(LW.C0, CFrame.new(-1.5, 0.5, 0) * angles(math.rad(30)*math.cos(sine/10), math.rad(5), math.rad(0)), 0.3)
RH.C0=clerp(RH.C0,cf(1.1,-.9,0)*angles(math.rad(0),math.rad(110),math.rad(0)),.3)
LH.C0=clerp(LH.C0,cf(-1.1,-.9,0)*angles(math.rad(0),math.rad(-70),math.rad(0)),.3)
handleweld.C0=clerp(handleweld.C0,cf(0,0,.3)*angles(math.rad(10),math.rad(0),math.rad(0)),.3)
end
end
end
if #Effects>0 then
for e=1,#Effects do
if Effects[e]~=nil then
local Thing=Effects[e]
if Thing~=nil then
local Part=Thing[1]
local Mode=Thing[2]
local Delay=Thing[3]
local IncX=Thing[4]
local IncY=Thing[5]
local IncZ=Thing[6]
if Thing[1].Transparency<=1 then
if Thing[2]=="Block1" then
Thing[1].CFrame=Thing[1].CFrame*euler(math.random(-50,50),math.random(-50,50),math.random(-50,50))
Mesh=Thing[1].Mesh
Mesh.Scale=Mesh.Scale+vt(Thing[4],Thing[5],Thing[6])
Thing[1].Transparency=Thing[1].Transparency+Thing[3]
elseif Thing[2]=="Cylinder" then
Mesh=Thing[1].Mesh
Mesh.Scale=Mesh.Scale+vt(Thing[4],Thing[5],Thing[6])
Thing[1].Transparency=Thing[1].Transparency+Thing[3]
elseif Thing[2]=="Blood" then
Mesh=Thing[7]
Thing[1].CFrame=Thing[1].CFrame*cf(0,.5,0)
Mesh.Scale=Mesh.Scale+vt(Thing[4],Thing[5],Thing[6])
Thing[1].Transparency=Thing[1].Transparency+Thing[3]
elseif Thing[2]=="Elec" then
Mesh=Thing[1].Mesh
Mesh.Scale=Mesh.Scale+vt(Thing[7],Thing[8],Thing[9])
Thing[1].Transparency=Thing[1].Transparency+Thing[3]
elseif Thing[2]=="Disappear" then
Thing[1].Transparency=Thing[1].Transparency+Thing[3]
end
else
Part.Parent=nil
table.remove(Effects,e)
end
end
end
end
end
end

--[[game:GetService("RunService").RenderStepped:connect(function()
for i,v in pairs (ShockModel:children()) do
if v.Transparency == 1 then break end
v.Transparency = v.Transparency + 0.05 v.CFrame = CFrame.new(0,math.rad(2),0)
local SM = v:findFirstChild("Mesh")
SM.Scale = SM.Scale + Vector3.new(1,0,1)
end
end)]]
end)

--DEX EXPLORER AND ANTICHEAT

local Tab = Window:NewTab("DELETE ANTICHEAT")
local Section = Tab:NewSection("TO DELETE ANTICHEAT")

Section:NewButton("Execute", "Made by yanros74", function()
game:GetService("Workspace").Configuration.AntiExploit:Destroy() 
end)

local Section = Tab:NewSection("TO DELETE ANTICHEAT")

Section:NewButton("Execute", "Made by yanros74", function()
game:GetService("ReplicatedStorage").Events.ForceEvents.AE:Destroy() 
end)

local Section = Tab:NewSection("DEX EXPLORER")

Section:NewButton("Open", "Made by yanros74", function()
loadstring(game:GetObjects('rbxassetid://2180084478')[1].Source)()
end)

local Section = Tab:NewSection("OTHER DEX EXPLORER")

Section:NewButton("Open", "Made by yanros74", function()
local rng = Random.new()

local charset = {}
for i = 48,  57 do table.insert(charset, string.char(i)) end
for i = 65,  90 do table.insert(charset, string.char(i)) end
for i = 97, 122 do table.insert(charset, string.char(i)) end
local function RandomCharacters(length)
  if length > 0 then
    return RandomCharacters(length - 1) .. charset[rng:NextInteger(1, #charset)]
  else
    return ""
  end
end

local Dex = game:GetObjects("rbxassetid://9553291002")[1]
syn.protect_gui(Dex)
Dex.Name = RandomCharacters(rng:NextInteger(5, 20))
Dex.Parent = game:GetService("CoreGui")
    
local function Load(Obj, Url)
local function GiveOwnGlobals(Func, Script)
    local Fenv = {}
    local RealFenv = {script = Script}
    local FenvMt = {}
    FenvMt.__index = function(a,b)
        if RealFenv[b] == nil then
            return getfenv()[b]
        else
            return RealFenv[b]
        end
    end
    FenvMt.__newindex = function(a, b, c)
        if RealFenv[b] == nil then
            getfenv()[b] = c
        else
            RealFenv[b] = c
        end
    end
    setmetatable(Fenv, FenvMt)
    setfenv(Func, Fenv)
    return Func
end

local function LoadScripts(Script)
    if Script.ClassName == "Script" or Script.ClassName == "LocalScript" then
        spawn(function()
            GiveOwnGlobals(loadstring(Script.Source, "=" .. Script:GetFullName()), Script)()
        end)
    end
    for i,v in pairs(Script:GetChildren()) do
        LoadScripts(v)
    end
end

LoadScripts(Obj)
end

Load(Dex)
end)

--ADMIN AND TOGGLE THING

local Tab = Window:NewTab("ADMIN AND TOGGLE")
local Section = Tab:NewSection("ADMIN AND TOGGLE")

Section:NewButton("Execute", "Made by yanros74", function()
loadstring(game:HttpGet(('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'),true))()
end)

local Section = Tab:NewSection("TOGGLE")
Section:NewKeybind("To Hide GUI", "Hide GUI", Enum.KeyCode.P, function()
	Library:ToggleUI()
end)

--CREDITS AND RESPAWN (READ FIRST)

local Tab = Window:NewTab("READ ME FIRST")
local Section = Tab:NewSection("made by yanros74")

Section:NewButton("Respawn", "yanros74", function()
game.Players.LocalPlayer.Character.Head:Destroy()
end)
