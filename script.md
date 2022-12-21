-- By Skylex?

local ScreenGui = Instance.new("ScreenGui")
local MainBox = Instance.new("Frame")
local UICorner = Instance.new("UICorner")
local TextLabel = Instance.new("TextLabel")
local UICorner_2 = Instance.new("UICorner")
local TextLabel_2 = Instance.new("TextLabel")
local UICorner_3 = Instance.new("UICorner")
local TextButton = Instance.new("TextButton")
local UICorner_4 = Instance.new("UICorner")
local hub = Instance.new("TextButton")
local UICorner_5 = Instance.new("UICorner")
local TextButton_2 = Instance.new("TextButton")
local UICorner_6 = Instance.new("UICorner")



ScreenGui.Parent = game.CoreGui

MainBox.Name = "MainBox"
MainBox.Parent = ScreenGui
MainBox.BackgroundColor3 = Color3.fromRGB(176, 130, 255)
MainBox.Position = UDim2.new(0.162534401, 0, 0.387301594, 0)
MainBox.Size = UDim2.new(0, 323, 0, 216)

UICorner.Parent = MainBox

TextLabel.Parent = MainBox
TextLabel.BackgroundColor3 = Color3.fromRGB(255, 10, 14)
TextLabel.BorderColor3 = Color3.fromRGB(145, 255, 0)
TextLabel.Position = UDim2.new(0, 0, 0.152423292, 0)
TextLabel.Size = UDim2.new(0, 323, 0, 16)
TextLabel.Font = Enum.Font.SourceSans
TextLabel.Text = ""
TextLabel.TextColor3 = Color3.fromRGB(0, 0, 0)
TextLabel.TextSize = 14.000

UICorner_2.Parent = TextLabel

TextLabel_2.Parent = MainBox
TextLabel_2.BackgroundColor3 = Color3.fromRGB(100, 100, 100)
TextLabel_2.Position = UDim2.new(-0.000338759273, 0, -0.00158762047, 0)
TextLabel_2.Size = UDim2.new(0, 151, 0, 23)
TextLabel_2.Font = Enum.Font.Unknown
TextLabel_2.Text = "DarkWare"
TextLabel_2.TextColor3 = Color3.fromRGB(38, 255, 0)
TextLabel_2.TextSize = 14.000

UICorner_3.Parent = TextLabel_2

TextButton.Parent = MainBox
TextButton.BackgroundColor3 = Color3.fromRGB(17, 0, 255)
TextButton.Position = UDim2.new(0.0362102389, 0, 0.283196628, 0)
TextButton.Size = UDim2.new(0, 107, 0, 26)
TextButton.Font = Enum.Font.SourceSans
TextButton.Text = "-givespeed [AUTO]"
TextButton.TextColor3 = Color3.fromRGB(0, 0, 0)
TextButton.TextSize = 14.000
TextButton.MouseButton1Click:Connect(function()
	print("Gived Speed!")
end)

UICorner_4.Parent = TextButton

hub.Name = "hub"
hub.Parent = MainBox
hub.BackgroundColor3 = Color3.fromRGB(17, 0, 255)
hub.Position = UDim2.new(0.0362102389, 0, 0.491529942, 0)
hub.Size = UDim2.new(0, 107, 0, 26)
hub.Font = Enum.Font.SourceSans
hub.Text = "-darkware"
hub.TextColor3 = Color3.fromRGB(0, 0, 0)
hub.TextSize = 14.000
hub.MouseButton1Click:Connect(function()
	loadstring(game:HttpGet("https://raw.githubusercontent.com/selecteduseromg343/new/main/README.md"))()
end)

UICorner_5.Parent = hub

TextButton_2.Parent = MainBox
TextButton_2.BackgroundColor3 = Color3.fromRGB(17, 0, 255)
TextButton_2.Position = UDim2.new(0.466550797, 0, 0.283196628, 0)
TextButton_2.Size = UDim2.new(0, 107, 0, 26)
TextButton_2.Font = Enum.Font.SourceSans
TextButton_2.Text = "-bypass"
TextButton_2.TextColor3 = Color3.fromRGB(0, 0, 0)
TextButton_2.TextSize = 14.000
TextButton_2.MouseButton1Click:Connect(function()
	print("Bypassed!")
end)


UICorner_6.Parent = TextButton_2

-- BySkylex
-- Leak + blacklist!

local function EAFVJMN_fake_script() -- TextButton.Script 
	local script = Instance.new('Script', TextButton)

	speed = 30 --16 is default
	
	function onPlayerRespawned(character)
		wait(1) --loading delay
		local player = game.Players:GetPlayerFromCharacter(character)
		local human = character:findFirstChild("Humanoid")
		if player ~= nil and human ~= nil then
			human.WalkSpeed = speed
		end
	end
	
	game.Workspace.ChildAdded:connect(onPlayerRespawned)
end
coroutine.wrap(EAFVJMN_fake_script)()
local function TDYJTZ_fake_script() -- MainBox.LocalScript 
	local script = Instance.new('LocalScript', MainBox)

	local UIS = game:GetService('UserInputService')
	local frame = script.Parent
	local dragToggle = nil
	local dragSpeed = 0
	local dragStart = nil
	local startPos = nil
	
	local function updateInput(input)
		local delta = input.Position - dragStart
		local position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X,
			startPos.Y.Scale, startPos.Y.Offset + delta.Y)
		game:GetService('TweenService'):Create(frame, TweenInfo.new(dragSpeed), {Position = position}):Play()
	end
	
	frame.InputBegan:Connect(function(input)
		if (input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch) then 
			dragToggle = true
			dragStart = input.Position
			startPos = frame.Position
			input.Changed:Connect(function()
				if input.UserInputState == Enum.UserInputState.End then
					dragToggle = false
				end
			end)
		end
	end)
	
	UIS.InputChanged:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
			if dragToggle then
				updateInput(input)
			end
		end
	end)
	
end
coroutine.wrap(TDYJTZ_fake_script)()
local function OOGCFG_fake_script() -- hub.Script 
	local script = Instance.new('Script', hub)

	
end
coroutine.wrap(OOGCFG_fake_script)()
