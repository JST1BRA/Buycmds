local Library = loadstring(game:HttpGet('https://raw.githubusercontent.com/Loco-CTO/UI-Library/main/VisionLibV2/source.lua'))()

Window = Library:Create({
	Name = "MOUSETRAP - KILLALL",
	Footer = "By ~ i h !",
	ToggleKey = Enum.KeyCode.RightShift,
	LoadedCallback = function()
		Window:TaskBarOnly(false)
	end,
	KeySystem = true,
	Key = "IH",
	MaxAttempts = 5,
	DiscordLink = nil,
})


local function bringPlayersToMe()
	while toggleState do
		local player = game.Players.LocalPlayer
		if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
			local playerPosition = player.Character.HumanoidRootPart.Position
			for _, otherPlayer in ipairs(game.Players:GetPlayers()) do
				if otherPlayer ~= player and otherPlayer.Character and otherPlayer.Character:FindFirstChild("HumanoidRootPart") then
					otherPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(playerPosition)
				end
			end
		end
		wait(0.01) -- don't touch this lmao
	end
end

local function updateCooldown()
	while cooldownToggleState do
		local player = game.Players.LocalPlayer
		if player and player.Character and player.Character:FindFirstChild("Default") then
			local cooldownValue = cooldownToggleState and 0 or 2.5
			player.Character.Default:SetAttribute("Cooldown", cooldownValue)
		end
		wait(0.01)
	end
end

Window:ChangeTogglekey(Enum.KeyCode.RightShift)

local Tab = Window:Tab({
	Name = "MOUSETRAP - KILLALL [~ I H !]",
	Icon = "rbxassetid://11396131982",
	Color = Color3.new(1, 0, 0),
})




local Section2 = Tab:Section({
	Name = "MOUSETRAP - KILLALL [~ I H !]",
})
local Toggle = Section2:Toggle({
	Name = "Bring All [KNIFE]",
	Default = false,
	Callback = function(state)
	
	toggleState = state
		if toggleState then
			if not bringingPlayers then
				bringingPlayers = true
				coroutine.wrap(bringPlayersToMe)()
			end
		else
			bringingPlayers = false
		end
	end,
})

local Dropdown = Section2:Dropdown({
	Name = "Soon",
	Items = { "Soon" },
	Callback = function(item)
	
		
	end,
})
    local Button = Section2:Button({
        Name = "Soon",
        Callback = function()
        
    
        end,
    })
local Section = Tab:Section({
	Name = "Misc",
})

local Button = Section:Button({
	Name = "Destroy library",
	Callback = function()
		Library:Destroy()
	end,
})

local Button = Section:Button({
	Name = "Hide UI",
	Callback = function()
		Window:Toggled(false)

		task.wait(3)

		Window:Toggled(true)
	end,
})

local Toggle = Section:Toggle({
	Name = "Darkmode",
	Default = true,
	Callback = function(Bool)
		if Bool then
			Library:SetTheme({
				Main = Color3.fromRGB(45, 45, 45),
				Secondary = Color3.fromRGB(31, 31, 31),
				Tertiary = Color3.fromRGB(31, 31, 31),
				Text = Color3.fromRGB(255, 255, 255),
				PlaceholderText = Color3.fromRGB(175, 175, 175),
				Textbox = Color3.fromRGB(61, 61, 61),
				NavBar = Color3.fromRGB(35, 35, 35),
				Theme = Color3.fromRGB(232, 202, 35),
			})
		else
			Library:SetTheme({
				Main = Color3.fromRGB(238, 238, 238),
				Secondary = Color3.fromRGB(194, 194, 194),
				Tertiary = Color3.fromRGB(163, 163, 163),
				Text = Color3.fromRGB(0, 0, 0),
				PlaceholderText = Color3.fromRGB(15, 15, 15),
				Textbox = Color3.fromRGB(255, 255, 255),
				NavBar = Color3.fromRGB(239, 239, 239),
				Theme = Color3.fromRGB(232, 55, 55),
			})
		end
	end,
})



local Button = Section:Button({
	Name = "Task Bar Only",
	Callback = function()
		Window:TaskBarOnly(true)

		task.wait(3)

		Window:TaskBarOnly(false)
	end,
})
