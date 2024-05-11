local previousPosition = game.Players.LocalPlayer.Character.HumanoidRootPart.Position

local function unequipTools()
    local character = game.Players.LocalPlayer.Character
    if character then
        for _, tool in pairs(character:GetChildren()) do
            if tool:IsA("Tool") then
                tool.Parent = game.Players.LocalPlayer.Backpack
            end
        end
    end
end

local function teleport()
    -- Teleport to the shop
    game.Players.LocalPlayer.Character:MoveTo(game.Workspace.Ignored.Shop["[High Armor] - $1061"].Head.Position)
    wait(0.01) -- Wait for 0.01 second
    unequipTools()
 

    -- Teleport back to the previous position
    wait(0.2)
       fireclickdetector(game.Workspace.Ignored.Shop["[High Armor] - $1061"].ClickDetector)
    game.Players.LocalPlayer.Character:MoveTo(previousPosition)
end

local function BuyAr()
    -- Teleport to the shop
    game.Players.LocalPlayer.Character:MoveTo(game.Workspace.Ignored.Shop["[AR] - $1061"].Head.Position)
       
         
    wait(0.01) -- Wait for 0.01 second
    unequipTools()
 

    -- Teleport back to the previous position
    wait(0.2)
       fireclickdetector(game.Workspace.Ignored.Shop["[AR] - $1061"].ClickDetector)
   
           wait(0.2)
    game.Players.LocalPlayer.Character:MoveTo(previousPosition)
end


local function BuyTac()
    -- Teleport to the shop
    game.Players.LocalPlayer.Character:MoveTo(game.Workspace.Ignored.Shop["[TacticalShotgun] - $1857"].Head.Position)
    wait(0.01) -- Wait for 0.01 second
    unequipTools()
 

    -- Teleport back to the previous position
    wait(0.2)
       fireclickdetector(game.Workspace.Ignored.Shop["[TacticalShotgun] - $1857"].ClickDetector)
    wait(0.2)
    game.Players.LocalPlayer.Character:MoveTo(previousPosition)
end

local function BuySm()
    -- Teleport to the shop
    game.Players.LocalPlayer.Character:MoveTo(game.Workspace.Ignored.Shop["[Surgeon Mask] - $27"].Head.Position)
    wait(0.01) -- Wait for 0.01 second
    unequipTools()
 

    -- Teleport back to the previous position
    wait(0.2)
       fireclickdetector(game.Workspace.Ignored.Shop["[Surgeon Mask] - $27"].ClickDetector)
    wait(0.2)
    game.Players.LocalPlayer.Character:MoveTo(previousPosition)
end


local function BuyAk()
    -- Teleport to the shop
    game.Players.LocalPlayer.Character:MoveTo(game.Workspace.Ignored.Shop["[AK47] - $2387"].Head.Position)
    wait(0.01) -- Wait for 0.01 second
    unequipTools()
 

    -- Teleport back to the previous position
    wait(0.2)
       fireclickdetector(game.Workspace.Ignored.Shop["[AK47] - $2387"].ClickDetector)
    wait(0.2)
    game.Players.LocalPlayer.Character:MoveTo(previousPosition)
end


local function BuySmg()
    -- Teleport to the shop
    game.Players.LocalPlayer.Character:MoveTo(game.Workspace.Ignored.Shop["[SMG] - $796"].Head.Position)
    wait(0.01) -- Wait for 0.01 second
    unequipTools()
 

    -- Teleport back to the previous position
    wait(0.2)
       fireclickdetector(game.Workspace.Ignored.Shop["[SMG] - $796"].ClickDetector)
    wait(0.2)
    game.Players.LocalPlayer.Character:MoveTo(previousPosition)
end



local function BuySr()
    -- Teleport to the shop
    game.Players.LocalPlayer.Character:MoveTo(game.Workspace.Ignored.Shop["[Silencer] - $583"].Head.Position)
    wait(0.01) -- Wait for 0.01 second
    unequipTools()
 

    -- Teleport back to the previous position
    wait(0.2)
       fireclickdetector(game.Workspace.Ignored.Shop["[Silencer] - $583"].ClickDetector)
    wait(0.2)
    game.Players.LocalPlayer.Character:MoveTo(previousPosition)
end



local function BuyRev()
    -- Teleport to the shop
    game.Players.LocalPlayer.Character:MoveTo(game.Workspace.Ignored.Shop["[Revolver] - $1379"].Head.Position)
    wait(0.01) -- Wait for 0.01 second
    unequipTools()
 

    -- Teleport back to the previous position
    wait(0.2)
       fireclickdetector(game.Workspace.Ignored.Shop["[Revolver] - $1379"].ClickDetector)
           wait(0.2)
    game.Players.LocalPlayer.Character:MoveTo(previousPosition)
end


local function BuyRpg()
    -- Teleport to the shop
    game.Players.LocalPlayer.Character:MoveTo(game.Workspace.Ignored.Shop["[RPG] - $6365"].Head.Position)
    wait(0.01) -- Wait for 0.01 second
    unequipTools()
 

    -- Teleport back to the previous position
    wait(0.2)
       fireclickdetector(game.Workspace.Ignored.Shop["[RPG] - $6365"].ClickDetector)
           wait(0.2)
    game.Players.LocalPlayer.Character:MoveTo(previousPosition)
end

local function BuyDb()
 game.Players.LocalPlayer.Character:MoveTo(game.Workspace.Ignored.Shop["[Double-Barrel SG] - $1485"].Head.Position)
    wait(0.01) -- Wait for 0.01 second
 
    -- Unequip all tools
    unequipTools()
    -- Teleport back to the previous position
    wait(0.2)
       fireclickdetector(game.Workspace.Ignored.Shop["[Double-Barrel SG] - $1485"].ClickDetector)
           wait(0.2)
    game.Players.LocalPlayer.Character:MoveTo(previousPosition)
end


-- Function to store the current position before teleporting
local function updatePreviousPosition()
    previousPosition = game.Players.LocalPlayer.Character.HumanoidRootPart.Position
end

-- Function to continuously update the original position every second
local function updateOriginalPosition()
    while true do
        updatePreviousPosition()
        wait(1) -- Update every second
    end
end

-- Start a coroutine to continuously update the original position
coroutine.wrap(updateOriginalPosition)()

-- Function to teleport the player to the shop and back

-- Define a variable to track the state of the feature
local dbEnabled = false

-- Function to toggle the state of the feature
local function toggleDb()
    dbEnabled = not dbEnabled
end



