local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()


local Window = Fluent:CreateWindow({
    Title = "PB Hub V8 Remake " .. Fluent.Version,
    SubTitle = "by Noly",
    TabWidth = 160,
    Size = UDim2.fromOffset(580, 460),
    Acrylic = true, -- The blur may be detectable, setting this to false disables blur entirely
    Theme = "Darker",
    MinimizeKey = Enum.KeyCode.LeftControl -- Used when theres no MinimizeKeybind
})


local alvodongc
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "Nome"
local Nzx = Instance.new("ImageButton")
ScreenGui.Parent = game.CoreGui

-- Criando o UICorner para deixar o botão redondo
local Estetica = Instance.new("UICorner")
Estetica.CornerRadius = UDim.new(1, 0) -- O "1" faz o botão ficar completamente redondo
Estetica.Parent = Nzx -- Aplica o UICorner ao botão Nzx

Nzx.Name = "Nzx"
Nzx.Parent = ScreenGui
Nzx.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Nzx.Position = UDim2.new(0.799450576, 0, 0.278925627, 0)
Nzx.Size = UDim2.new(0, 50, 0, 50)
Nzx.Visible = true
Nzx.Draggable = true     
Nzx.Active = true     
Nzx.Selectable = true
Nzx.Image = "rbxassetid://86898373680592" -- Id da imagem aqui

-- Função para alternar a visibilidade de "alvodongc"
for i, v in pairs(game.CoreGui:GetDescendants()) do
    if v.Name == "CanvasGroup" then
        alvodongc = v.Parent
    end
end

local function FVGE_fake_script()
    Nzx.MouseButton1Up:Connect(function()
        task.wait()
        if not toggle then
            toggle = true
            alvodongc.Visible = true
        else
            toggle = false
            alvodongc.Visible = false
        end
    end)
end
coroutine.wrap(FVGE_fake_script)()


local Tab = Window:AddTab({ Title = "Welcome", Icon = "home" })


Tab:AddParagraph({
    Title = "Obrigado por Usa",
    Content = ""
})


Tab:AddParagraph({
    Title = "Hub em atualizações",
    Content = ""
})


local Tab = Window:AddTab({ Title = "Troll", Icon = "skull" })

Tab:AddParagraph({
    Title = "<View Goto>",
    Content = ""
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

local Dropdown = Tab:AddDropdown("Dropdown", {
    Title = "Lista de Jogadores",
    Values = gotoPlayerList,
    Multi = false,
    Default = 1,
})

Dropdown:OnChanged(function(playerName)
    selectedGotoPlayer = playerName
end)


Tab:AddButton({
   Title = "Reset Player Lits",
   Description = "Very important button",
   Callback = function()
       updatePlayerList()
playerDropdown:Refresh(gotoPlayerList, true)
print("Clicked!")
   end
})

local Toggle = Tab:AddToggle("MyToggle", {Title = "View", Default = false })

Toggle:OnChanged(function(state)
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
end)

local Toggle = Tab:AddToggle("MyToggle", {Title = "Follow", Default = false })

Toggle:OnChanged(function(state)
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
end)


Tab:AddButton({
   Title = "Goto",
   Description = "Very important button",
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
 print("Clicked!")
   end
})


Tab:AddParagraph({
    Title = "<Car>",
    Content = ""
})


local bloco = Instance.new("Part")
bloco.Size = Vector3.new(4993, 15, 4999)
bloco.Position = Vector3.new(101, -446, -180)
bloco.Anchored = true
bloco.BrickColor = BrickColor.new("Bright White")
bloco.Parent = workspace

bloco.Touched:Connect(function(hit)
    local player = game.Players:GetPlayerFromCharacter(hit.Parent)
    if player then
       print("ola mundo")
wait(0.8) game:GetService("ReplicatedStorage").RE["1Ca1r"]:FireServer("DeleteAllVehicles")
    end
end)
wait(0.2)
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()

character:WaitForChild("HumanoidRootPart").Changed:Connect(function()
    if character.HumanoidRootPart.Position.Y < -50 then
        character:SetPrimaryPartCFrame(CFrame.new(0, 10, 0))
    end
end)
wait(0.1)


local Players = game:GetService("Players")
local Workspace = game:GetService("Workspace")
local RunService = game:GetService("RunService")

local playerNames = {}
for _, player in pairs(Players:GetPlayers()) do
    table.insert(playerNames, player.Name)
end

local selectedPlayerName = nil

local Dropdown = Tab:AddDropdown("Dropdown", {
    Title = "Target",
    Values = playerNames,
    Multi = false,
    Default = 1,
})

Dropdown:OnChanged(function(selected)
    selectedPlayerName = selected
end)


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
   Title = "Car kill",
   Description = "Very important button",
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
print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Boat Fling",
   Description = "Very important button",
   Callback = function()
          if selectedPlayerName then
            local selectedPlayer = game.Players:FindFirstChild(selectedPlayerName)
            if selectedPlayer then
                local Player = game.Players.LocalPlayer
                local Character = Player.Character
                local Humanoid = Character and Character:FindFirstChildOfClass("Humanoid")
                local RootPart = Character and Character:FindFirstChild("HumanoidRootPart")
                local Vehicles = game.Workspace:FindFirstChild("Vehicles")
                local OldPos = RootPart and RootPart.CFrame

                if RootPart and Vehicles then
                    local PCar = Vehicles:FindFirstChild(Player.Name.."Car")
                    if not PCar then
                        RootPart.CFrame = CFrame.new(-3, -4, 2105)
                        task.wait(0.5)
                        game:GetService("ReplicatedStorage").RE["1Ca1r"]:FireServer("PickingBoat", "MilitaryBoatFree")
                        task.wait(0.5)
                        PCar = Vehicles:FindFirstChild(Player.Name.."Car")

                        if PCar then
                            local Seat = PCar:FindFirstChild("Body") and PCar.Body:FindFirstChild("VehicleSeat")
                            if Seat then
                                repeat
                                    task.wait()
                                    RootPart.CFrame = Seat.CFrame * CFrame.new(0, 2, 0)
                                until Humanoid and Humanoid.Sit
                            end
                        end
                    end

                    local TargetC = selectedPlayer.Character
                    local TargetH = TargetC and TargetC:FindFirstChildOfClass("Humanoid")
                    local TargetRP = TargetC and TargetC:FindFirstChild("HumanoidRootPart")

                    if PCar and TargetC and TargetH and TargetRP then
                        if not TargetH.Sit then
                            while not TargetH.Sit do
                                task.wait()
                                PCar:SetPrimaryPartCFrame(TargetRP.CFrame * CFrame.new(0, -2, 0))
                            end
                            task.wait(0.1)

                            local AngularVelocity = Instance.new("BodyAngularVelocity")
                            AngularVelocity.AngularVelocity = Vector3.new(70, 0, 0)
                            AngularVelocity.MaxTorque = Vector3.new(math.huge, math.huge, math.huge)
                            AngularVelocity.Parent = PCar.PrimaryPart

                            task.wait(1)

                            local launchDirection = Vector3.new(math.random(-1, 1), 1, math.random(-1, 1)).unit * 50
                            local BodyVelocity = Instance.new("BodyVelocity")
                            BodyVelocity.Velocity = launchDirection
                            BodyVelocity.MaxForce = Vector3.new(math.huge, math.huge, math.huge)
                            BodyVelocity.Parent = PCar.PrimaryPart

                            task.wait(0.5)
                            BodyVelocity:Destroy()
                            AngularVelocity:Destroy()

                            if Humanoid then Humanoid.Sit = false end
                            task.wait(0.1)
                            if RootPart then RootPart.CFrame = OldPos end
                        end
                    end
                end
            else
                print("tu tento pega um jogador que kitou ou que ta bugado")
            end
        else
            print("seleciona um jogador filho da puta animal")
        end
 print("Clicked!")
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
   Title = "Car Fling",
   Description = "Very important button",
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
 print("Clicked!")
   end
})


Tab:AddParagraph({
    Title = "<Fling Couch Bring Player>",
    Content = ""
})

-- VariÃƒÂ¡veis de controle
local teleporting = false
local flingEnabled = false
local viewEnabled = false
local selectedPlayer = nil
local flingSpeed = 99999  -- Aumentando a velocidade para um Fling mais forte

-- FunÃƒÂ§ÃƒÂ£o para teleporte contÃƒÂ­nuo
local function startTeleport()
    teleporting = true
    while teleporting do
        task.wait(0.10)

        local targetCharacter = selectedPlayer.Character
        if not targetCharacter then
            teleporting = false
            return
        end

        local targetHRP = targetCharacter:FindFirstChild("HumanoidRootPart")
        if not targetHRP then
            teleporting = false
            return
        end

        -- Teleporte contÃƒÂ­nuo
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = targetHRP.CFrame

        -- Aplica Fling mais forte se estiver ativado
        if flingEnabled then
            game.Players.LocalPlayer.Character.HumanoidRootPart.Velocity = Vector3.new(
                math.random(-flingSpeed, flingSpeed), 
                flingSpeed * 2,  -- Dando um impulso mais forte no eixo Y
                math.random(-flingSpeed, flingSpeed)
            )
            game.Players.LocalPlayer.Character.HumanoidRootPart.RotVelocity = Vector3.new(flingSpeed * 1.5, flingSpeed * 1.5, flingSpeed * 1.5)  -- Maior rotaÃƒÂ§ÃƒÂ£o
        end
    end
end

-- FunÃƒÂ§ÃƒÂ£o para parar o teleporte
local function stopTeleport()
    teleporting = false
end

-- FunÃƒÂ§ÃƒÂ£o para atualizar a lista de jogadores
local function updatePlayerList()
    local playerNames = {}
    for _, player in ipairs(game.Players:GetPlayers()) do
        if player ~= game.Players.LocalPlayer then
            table.insert(playerNames, player.Name)
        end
    end
    return playerNames
end

-- FunÃƒÂ§ÃƒÂ£o para ativar/desativar o View
local function enableView(targetPlayer)
    if not targetPlayer or not targetPlayer.Character then return end

    local camera = workspace.CurrentCamera
    camera.CameraSubject = targetPlayer.Character:FindFirstChild("Humanoid") or targetPlayer.Character
    camera.CameraType = Enum.CameraType.Custom
end

local function disableView()
    local camera = workspace.CurrentCamera
    camera.CameraSubject = game.Players.LocalPlayer.Character:FindFirstChild("Humanoid")
    camera.CameraType = Enum.CameraType.Custom
end

-- Reconectar View apÃƒÂ³s morte
game.Players.LocalPlayer.CharacterAdded:Connect(function()
    if viewEnabled and selectedPlayer then
        enableView(selectedPlayer)
    end
end)


local Dropdown = Tab:AddDropdown("Dropdown", {
    Title = "selecionar jogando",
    Values = updatePlayerList(),
    Multi = false,
    Default = 1,
})

Dropdown:OnChanged(function(state)
    selectedPlayer = game.Players:FindFirstChild(state)
end)

local Toggle = Tab:AddToggle("MyToggle", {Title = "Fling Couch", Default = false })

Toggle:OnChanged(function(state)
    flingEnabled = state
        if flingEnabled then
            startTeleport()
        else
            stopTeleport()
        end
end)


local playerTextbox

local function findPlayerByName(partialName)
    for _, player in pairs(game.Players:GetPlayers()) do
        if string.find(player.Name:lower(), partialName:lower()) or 
           string.find(player.DisplayName:lower(), partialName:lower()) then
            return player
        end
    end
    return nil
end

local function changeCharacterSize(sizeType, sizeValue)
    local args = {
        [1] = sizeType,
        [2] = sizeValue
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clothe1s"):FireServer(unpack(args))
end

local function equipAllItems()
    local myPlayer = game.Players.LocalPlayer
    local myCharacter = myPlayer.Character

    for _, tool in pairs(myPlayer.Backpack:GetChildren()) do
        if tool:IsA("Tool") then
            tool.Parent = myCharacter
            wait(0.1)
        end
    end
end

local function invokeServer()
    local args = {
        [1] = "PickingTools",
        [2] = "Couch"
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
end

local function clearAllTools()
    local args = {
        [1] = "ClearAllTools"
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))
end

local function isPlayerMoving(player)
    local character = player.Character
    if character then
        local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
        if humanoidRootPart then
            return humanoidRootPart.Velocity.Magnitude > 0.1
        end
    end
    return false
end

local function teleportToPlayer(targetPlayer, mode)
    local myPlayer = game.Players.LocalPlayer
    local myCharacter = myPlayer.Character
    local targetCharacter = targetPlayer.Character

    if not myCharacter or not targetCharacter then return end

    local originalPosition = myCharacter.PrimaryPart.CFrame
    local myHumanoid = myCharacter:FindFirstChildWhichIsA("Humanoid")

    local function executeTeleport()
        while true do
            if not targetPlayer.Parent then
                OrionLib:MakeNotification({
                    Name = "Player left",
                    Content = "The player has left the game.",
                    Time = 5
                })
                break
            end

            local humanoid = targetCharacter:FindFirstChildWhichIsA("Humanoid")
            if humanoid and humanoid:GetState() == Enum.HumanoidStateType.Seated then
                if mode == "fling" then
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(1e8, 1e8, 1e8))
                    wait(0.7)
                    clearAllTools()
                    changeCharacterSize("CharacterSizeUp", 1)
                elseif mode == "kill" then
                    local distantPosition = CFrame.new(176.308655, -496.272827, 153.928467, 0.444366872, 0.485874146, 0.75263828, -2.14771028e-08, 0.840143502, -0.54236412, -0.895844877, 0.240143502, 0.54236412)
                    myCharacter:SetPrimaryPartCFrame(distantPosition)
                    wait(0.7)
                    clearAllTools()
                    changeCharacterSize("CharacterSizeUp", 1)
                elseif mode == "bring" then
                    wait(0.01)
                    myCharacter:SetPrimaryPartCFrame(originalPosition)
                    if myHumanoid then
                        myHumanoid.PlatformStand = true
                        wait(1)
                        myHumanoid.PlatformStand = false
                    end
                    wait(0.7)
                    clearAllTools()
                    changeCharacterSize("CharacterSizeUp", 1)
                end
                break
            end

            local targetPosition = targetCharacter.PrimaryPart.Position
            local forwardDirection = targetCharacter.PrimaryPart.CFrame.LookVector
            local rightDirection = targetCharacter.PrimaryPart.CFrame.RightVector
            local upwardAdjustment = Vector3.new(0, 1, 0)

            if isPlayerMoving(targetPlayer) then
                local newPosition = targetPosition + forwardDirection * 25 + upwardAdjustment
                myCharacter:SetPrimaryPartCFrame(CFrame.new(newPosition))
                wait(0.1)
            else
                if mode == "kill" then
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition + rightDirection * 2 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition - rightDirection * 2 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition + forwardDirection * 5 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition - forwardDirection * 2 + upwardAdjustment))
                    wait(0.05)
                else
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition + forwardDirection * 5 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition + rightDirection * 2 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition - rightDirection * 2 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition - forwardDirection * 5 + upwardAdjustment))
                    wait(0.05)
                end
            end
        end
    end

    spawn(function()
        changeCharacterSize("CharacterSizeDown", 0.55)
        invokeServer()
        wait(1)
        equipAllItems()
        if myHumanoid then
            myHumanoid.PlatformStand = false
        end
        executeTeleport()
    end)
end


local playerTextbox

local function findPlayerByName(partialName)
    for _, player in pairs(game.Players:GetPlayers()) do
        if string.find(player.Name:lower(), partialName:lower()) or 
           string.find(player.DisplayName:lower(), partialName:lower()) then
            return player
        end
    end
    return nil
end

local function changeCharacterSize(sizeType, sizeValue)
    local args = {
        [1] = sizeType,
        [2] = sizeValue
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clothe1s"):FireServer(unpack(args))
end

local function equipAllItems()
    local myPlayer = game.Players.LocalPlayer
    local myCharacter = myPlayer.Character

    for _, tool in pairs(myPlayer.Backpack:GetChildren()) do
        if tool:IsA("Tool") then
            tool.Parent = myCharacter
            wait(0.1)
        end
    end
end

local function invokeServer()
    local args = {
        [1] = "PickingTools",
        [2] = "Couch"
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
end

local function clearAllTools()
    local args = {
        [1] = "ClearAllTools"
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clea1rTool1s"):FireServer(unpack(args))
end

local function isPlayerMoving(player)
    local character = player.Character
    if character then
        local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
        if humanoidRootPart then
            return humanoidRootPart.Velocity.Magnitude > 0.1
        end
    end
    return false
end

local function teleportToPlayer(targetPlayer, mode)
    local myPlayer = game.Players.LocalPlayer
    local myCharacter = myPlayer.Character
    local targetCharacter = targetPlayer.Character

    if not myCharacter or not targetCharacter then return end

    local originalPosition = myCharacter.PrimaryPart.CFrame
    local myHumanoid = myCharacter:FindFirstChildWhichIsA("Humanoid")

    local function executeTeleport()
        while true do
            if not targetPlayer.Parent then
                
                break
            end

            local humanoid = targetCharacter:FindFirstChildWhichIsA("Humanoid")
            if humanoid and humanoid:GetState() == Enum.HumanoidStateType.Seated then
                if mode == "fling" then
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(1e8, 1e8, 1e8))
                    wait(0.7)
                    clearAllTools()
                    changeCharacterSize("CharacterSizeUp", 1)
                elseif mode == "kill" then
                    local distantPosition = CFrame.new(176.308655, -496.272827, 153.928467, 0.444366872, 0.485874146, 0.75263828, -2.14771028e-08, 0.840143502, -0.54236412, -0.895844877, 0.240143502, 0.54236412)
                    myCharacter:SetPrimaryPartCFrame(distantPosition)
                    wait(0.7)
                    clearAllTools()
                    changeCharacterSize("CharacterSizeUp", 1)
                elseif mode == "bring" then
                    wait(0.01)
                    myCharacter:SetPrimaryPartCFrame(originalPosition)
                    if myHumanoid then
                        myHumanoid.PlatformStand = true
                        wait(1)
                        myHumanoid.PlatformStand = false
                    end
                    wait(0.7)
                    clearAllTools()
                    changeCharacterSize("CharacterSizeUp", 1)
                end
                break
            end

            local targetPosition = targetCharacter.PrimaryPart.Position
            local forwardDirection = targetCharacter.PrimaryPart.CFrame.LookVector
            local rightDirection = targetCharacter.PrimaryPart.CFrame.RightVector
            local upwardAdjustment = Vector3.new(0, 1, 0)

            if isPlayerMoving(targetPlayer) then
                local newPosition = targetPosition + forwardDirection * 25 + upwardAdjustment
                myCharacter:SetPrimaryPartCFrame(CFrame.new(newPosition))
                wait(0.1)
            else
                if mode == "kill" then
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition + rightDirection * 2 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition - rightDirection * 2 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition + forwardDirection * 5 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition - forwardDirection * 2 + upwardAdjustment))
                    wait(0.05)
                else
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition + forwardDirection * 5 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition + rightDirection * 2 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition - rightDirection * 2 + upwardAdjustment))
                    wait(0.05)
                    myCharacter:SetPrimaryPartCFrame(CFrame.new(targetPosition - forwardDirection * 5 + upwardAdjustment))
                    wait(0.05)
                end
            end
        end
    end

    spawn(function()
        changeCharacterSize("CharacterSizeDown", 0.55)
        invokeServer()
        wait(1)
        equipAllItems()
        if myHumanoid then
            myHumanoid.PlatformStand = false
        end
        executeTeleport()
    end)
end


local Input = Tab:AddInput("Input", {
    Title = "Nick do Player",
    Default = "Default",
    Placeholder = "Placeholder",
    Numeric = false, -- Only allows numbers
    Finished = false, -- Only calls callback when you press enter
    Callback = function(state)
        playerTextbox = state
    end
})

Input:OnChanged(function()
    print("Input updated:", Input.Value)
end)


Tab:AddButton({
   Title = "Bring",
   Description = "Very important button",
   Callback = function()
     local targetPlayer = findPlayerByName(playerTextbox)
        if targetPlayer then
            teleportToPlayer(targetPlayer, "bring")
        else
        end
  print("Clicked!")
   end
})


Tab:AddParagraph({
    Title = "<Ban kill Couch Casa 11 Castelo>",
    Content = ""
})


-- Função para teletransportar o jogador local próximo do jogador alvo
function TeleportPlayer(teleportTime, playerName)
    local player = game.Players.LocalPlayer
    local character = player.Character
    if not character then return end

    local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
    if not humanoidRootPart then return end

    local originalPosition = humanoidRootPart.CFrame
    local targetPlayer = nil

    -- Encontra o jogador alvo pelo nome ou nome de exibição
    for _, p in ipairs(game.Players:GetPlayers()) do
        if (string.find(p.Name:lower(), playerName:lower()) or string.find(p.DisplayName:lower(), playerName:lower())) then
            targetPlayer = p
            break
        end
    end

    if not targetPlayer then
        warn("Jogador específico não encontrado.")
        return
    end

    local targetCharacter = targetPlayer.Character
    if targetCharacter and targetCharacter:FindFirstChild("HumanoidRootPart") then
        local targetPosition = targetCharacter.HumanoidRootPart.Position

        -- Função para realizar o "blink" (teleporte rápido)
        local function blink()
            humanoidRootPart.CFrame = CFrame.new(targetPosition + Vector3.new(5, 0, 0))
            wait(0.1)
            humanoidRootPart.CFrame = originalPosition
            wait(0.1)
        end

        local endTime = tick() + teleportTime
        while tick() < endTime do
            blink()
        end
    else
        warn("O jogador específico não está disponível.")
    end
end

-- Serviços do Roblox
local playerService = game:GetService("Players")
local replicatedStorage = game:GetService("ReplicatedStorage")
local localPlayer = playerService.LocalPlayer

-- Função para banir o jogador da "casa"
local function banPlayer(playerName)
    if playerName == localPlayer.Name then
        print("Você não pode se banir da sua própria casa.")
        return
    end

    print("Banindo o jogador:", playerName)
    local targetPlayer = playerService:FindFirstChild(playerName)
    if targetPlayer then
        local args = {"BanPlayerFromHouse", targetPlayer, targetPlayer.Character}
        replicatedStorage.RE:FindFirstChild("1Playe1rTrigge1rEven1t"):FireServer(unpack(args))
    else
        print("Jogador alvo não encontrado.")
    end
end

-- Teletransporta o jogador e realiza o banimento
local function teleportToCoordinateAndBan(playerName)
    if playerName == localPlayer.Name then
        print("Você não pode se banir da sua própria casa.")
        return
    end

    print("Teleportando para a coordenada e banindo...")
    local teleportPosition = Vector3.new(-20, 19, 464)
    localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(teleportPosition)
    wait(0.2)
    banPlayer(playerName)
end

-- Função de fling e banimento até o jogador sentar
local function flingUntilSeatCouchAndBan(targetPlayerName)
    if targetPlayerName == localPlayer.Name then
        print("Você não pode se banir da sua própria casa.")
        return
    end

    local targetPlayer = playerService:FindFirstChild(targetPlayerName)
    if targetPlayer and targetPlayer.Character and targetPlayer.Character:FindFirstChild("HumanoidRootPart") then
        local targetPosition = targetPlayer.Character.HumanoidRootPart.CFrame
        isFlinging = true

        while isFlinging do
            -- Movimenta o jogador local ao redor do alvo
            targetPosition = targetPlayer.Character.HumanoidRootPart.CFrame
            localPlayer.Character.HumanoidRootPart.CFrame = targetPosition * CFrame.new(10, 0, 0)
            wait(0)
            localPlayer.Character.HumanoidRootPart.CFrame = targetPosition * CFrame.new(0, 6, 0)
            wait(0)
            localPlayer.Character.HumanoidRootPart.CFrame = targetPosition * CFrame.new(0, 0, 6)
            wait(0)
            localPlayer.Character.HumanoidRootPart.CFrame = targetPosition * CFrame.new(0, 0, -6)
            wait(0)
            localPlayer.Character.HumanoidRootPart.CFrame = targetPosition * CFrame.new(-10, 0, 0)
            wait(0)
            localPlayer.Character.HumanoidRootPart.CFrame = targetPosition * CFrame.new(0, -8, 0)
            wait(0)

            -- Verifica se o jogador alvo sentou
            if targetPlayer.Character.Humanoid.SeatPart then
                isFlinging = false
            end
        end

        teleportToCoordinateAndBan(targetPlayerName)
    else
        print("Jogador alvo não encontrado ou inválido.")
    end
end

-- Monitorar a morte do jogador alvo e reiniciar o banimento
local function monitorPlayerDeath(targetPlayerName)
    while loopBanCouchEnabled do
        local targetPlayer = playerService:FindFirstChild(targetPlayerName)
        if targetPlayer and targetPlayer.Character and targetPlayer.Character:FindFirstChild("Humanoid") then
            if targetPlayer.Character.Humanoid.Health <= 0 then
                print("Jogador alvo morreu. Reiniciando o banimento...")
                flingUntilSeatCouchAndBan(targetPlayerName)
            end
        end
        wait(0)
    end
end

-- Encontra um jogador pelo nome parcial
local function findPlayerByPartialName(partialName)
    partialName = partialName:lower()
    for _, player in ipairs(playerService:GetPlayers()) do
        local playerName = player.Name:lower()
        local firstName = playerName:match("^%w+")
        if (playerName:find(partialName, 1, true) or (firstName and firstName:find(partialName, 1, true))) and (player ~= localPlayer) then
            return player.Name
        end
    end
    return nil
end

-- Previne a morte do jogador local
local function preventDeath()
    if localPlayer.Character and localPlayer.Character:FindFirstChild("Humanoid") then
        local humanoid = localPlayer.Character.Humanoid
        humanoid:GetPropertyChangedSignal("Health"):Connect(function()
            if humanoid.Health < 0 then
                humanoid.Health = 100
            end
        end)
    end
end


local Input = Tab:AddInput("Input", {
    Title = "Input",
    Default = "Default",
    Placeholder = "Placeholder",
    Numeric = false, -- Only allows numbers
    Finished = false, -- Only calls callback when you press enter
    Callback = function(playerName)
   local foundPlayer = findPlayerByPartialName(playerName)
        if foundPlayer then
            selectedBanCouchPlayer = foundPlayer
            print("Jogador selecionado para Ban Couch:", foundPlayer)
            if loopBanCouchEnabled then
                spawn(function() monitorPlayerDeath(selectedBanCouchPlayer) end)
            end
        else
            print("Jogador não encontrado ou você selecionou a si mesmo.")
        end
     print("Input changed:", Value)
    end
})

Input:OnChanged(function()
    print("Input updated:", Input.Value)
end)


Tab:AddButton({
   Title = "ban house",
   Description = "Very important button",
   Callback = function()
   if selectedBanCouchPlayer then
            flingUntilSeatCouchAndBan(selectedBanCouchPlayer)
            preventDeath()
        else
            print("Nenhum jogador selecionado.")
        end
    print("Clicked!")
   end
})


Tab:AddParagraph({
    Title = "<Lag All>",
    Content = ""
})


local toggles = {
    LagGhostMeterV2 = false
}

local function clickNormally(object)
    local clickDetector = object:FindFirstChildWhichIsA("ClickDetector")
    if clickDetector then
        fireclickdetector(clickDetector) -- Clica normalmente
    end
end

local function lagarServer2()
    local ghostMeterPath = workspace:FindFirstChild("WorkspaceCom"):FindFirstChild("001_GiveTools"):FindFirstChild("GhostMeter")
    if ghostMeterPath then
        while toggles.LagGhostMeterV2 do
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = ghostMeterPath.CFrame
            clickNormally(ghostMeterPath)
            wait(0) -- Executa rapidamente
        end
    else
        warn("Item GhostMeter não encontrado.")
    end
end



local Toggle = Tab:AddToggle("MyToggle", {Title = "Lag v2 Toggle Ghost Mater(crash)", Default = false })

Toggle:OnChanged(function(state)
    toggles.LagGhostMeterV2 = state
        if state then
            spawn(lagarServer2) -- Executa o lag em uma nova thread
        else
            print("Lag Ghost Meter V2 desligado.")
        end
end)


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


local Toggle = Tab:AddToggle("MyToggle", {Title = "Dupe basketball", Default = false })

Toggle:OnChanged(function(state)
 toggles.DupeBasketball = state
        if state then
            local basketballPath = workspace:FindFirstChild("WorkspaceCom"):FindFirstChild("001_GiveTools"):FindFirstChild("Basketball")
            spawn(function()
                dupeItem(basketballPath, 9999999999999999999999999999999999999)
            end)
        else
            print("Dupe Basketball desligado.")
        end
end)


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


local Toggle = Tab:AddToggle("MyToggle", {Title = "Dupe extinto", Default = false })

Toggle:OnChanged(function(state)
    toggles.DupeExtintor = state
        if state then
            local fireXPath = workspace:FindFirstChild("WorkspaceCom"):FindFirstChild("001_GiveTools"):FindFirstChild("FireX")
            spawn(function()
                dupeItem(fireXPath, 999999999999999999999999999999999999999)
            end)
        else
            print("Dupe Extintor desligado.")
        end
end)



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


local Toggle = Tab:AddToggle("MyToggle", {Title = "Dupe Book", Default = false })

Toggle:OnChanged(function(state)
    toggles.DupeBook = state
        if state then
            local bookPath = workspace:FindFirstChild("WorkspaceCom"):FindFirstChild("001_DayCare"):FindFirstChild("Tools"):FindFirstChild("Book")
            spawn(function()
                dupeItem(bookPath, 99999999999999999999999999999999999)
            end)
        else
            print("Dupe Book desligado.")
        end
end)



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


local Toggle = Tab:AddToggle("MyToggle", {Title = "Dupe Maca hospital", Default = false })

Toggle:OnChanged(function(state)
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
end)


Tab:AddButton({
   Title = "Lag Taser",
   Description = "Very important button",
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
   print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Lag Bomb",
   Description = "Very important button",
   Callback = function()
      local function duplicarBomb()
    local Player = game.Players.LocalPlayer
    local Character = Player.Character or Player.CharacterAdded:Wait()
    local RootPart = Character:WaitForChild("HumanoidRootPart")
    local Storage = game:GetService("Workspace"):FindFirstChild("WorkspaceCom") 
        and game:GetService("Workspace").WorkspaceCom["001_CriminalWeapons"].GiveTools

    if Storage and Storage:FindFirstChild("Bomb") then
        local Bomb = Storage:FindFirstChild("Bomb")
        local OldPos = RootPart.CFrame

        for i = 1, 12 do
            RootPart.CFrame = Bomb.CFrame
            fireclickdetector(Bomb:FindFirstChild("ClickDetector"))
            task.wait(0)
        end

        RootPart.CFrame = OldPos
    else
        warn("Erro ao encontrar a Bomb! Tente novamente.")
    end
end

while true do
    duplicarBomb()
    task.wait(0.001)
end
 print("Clicked!")
   end
})


local Tab = Window:AddTab({ Title = "Tools", Icon = "axe" })

Tab:AddButton({
   Title = "Pega cartão da agência",
   Description = "Very important button",
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
   print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Pegar Cartão da elétrica",
   Description = "Very important button",
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
  print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Pegar Arco",
   Description = "Very important button",
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
print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Pegar Crystal 1",
   Description = "Very important button",
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
 print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Pega Crystal 2",
   Description = "Very important button",
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
  print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Agência Book",
   Description = "Very important button",
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
  print("Clicked!")
   end
})


Tab:AddButton({
   Title = "OldKey",
   Description = "Very important button",
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
  print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Arma De Assalto",
   Description = "Very important button",
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
 print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Shot Gun",
   Description = "Very important button",
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
print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Couch",
   Description = "Very important button",
   Callback = function()
       local args = {
                [1] = "PickingTools",
                [2] = "Couch"
            }
            game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))
print("Clicked!")
   end
})


local Tab = Window:AddTab({ Title = "Car", Icon = "car" })


Tab:AddParagraph({
    Title = "Car Music[Premium]",
    Content = ""
})


local Input = Tab:AddInput("Input", {
    Title = "Music ID",
    Default = "",
    Placeholder = "Placeholder",
    Numeric = false, -- Only allows numbers
    Finished = false, -- Only calls callback when you press enter
    Callback = function(Value)
        -- Esta função é chamada sempre que o usuário insere um valor na TextBox.
        -- Podemos armazenar o valor em uma variável global ou em uma variável local.
        musicId = value
    end
})

Input:OnChanged(function()
    print("Input updated:", Input.Value)
end)


Tab:AddButton({
   Title = "Play Music Car [Gamepass Premium]",
   Description = "Very important button",
   Callback = function()
       -- Verifica se um ID de música foi inserido na TextBox
        if musicId and musicId ~= "" then
            -- Chama o evento para tocar o som com base no ID inserido
            local args = {
                [1] = "PickingCarMusicText",
                [2] = musicId  -- Usar o ID de música inserido na TextBox
            }
            game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sCa1r"):FireServer(unpack(args))
        else
            -- Se nenhum ID foi inserido, você pode adicionar um aviso ou mensagem para o usuário
            print("Por favor, insira um ID de música válido na TextBox.")
        end
print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Spawn School Bus",
   Description = "Very important button",
   Callback = function()
       local args = {
            [1] = "PickingCar",
            [2] = "SchoolBus"
        }
        game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer(unpack(args))
print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Spawn Truck",
   Description = "Very important button",
   Callback = function()
       local args = {
            [1] = "PickingCar",
            [2] = "Semi"
        }
        game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer(unpack(args))
print("Clicked!")
   end
})


local Tab = Window:AddTab({ Title = "House", Icon = "home" })


Tab:AddParagraph({
    Title = "<Edições De Casas>",
    Content = ""
})


-- Variável para armazenar a mensagem inserida pelo usuário para a biografia da casa
local houseBioMessage = ""


local Input = Tab:AddInput("Input", {
    Title = "Insira a bio da casa",
    Default = "",
    Placeholder = "Placeholder",
    Numeric = false, -- Only allows numbers
    Finished = false, -- Only calls callback when you press enter
    Callback = function(Value)
        houseBioMessage = value
    end
})

Input:OnChanged(function()
    print("Input updated:", Input.Value)
end)


Tab:AddButton({
   Title = "Adicionar A Bio Dá casa",
   Description = "Very important button",
   Callback = function()
    -- Verificar se a mensagem não está vazia
        if houseBioMessage and houseBioMessage ~= "" then
            local args = {
                [1] = "BusinessName",
                [2] = houseBioMessage
            }
            -- Definir a biografia da casa com a mensagem inserida pelo usuário
            game:GetService("ReplicatedStorage").RE:FindFirstChild("1RPHous1eEven1t"):FireServer(unpack(args))
            print("A biografia da casa foi definida com a mensagem:", houseBioMessage)
        else
            print("Por favor, insira uma mensagem válida para definir a biografia da casa.")
        end
   print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Abri/Fechar As Portas",
   Description = "Very important button",
   Callback = function()
       local args = {
            [1] = "LockDoors"
        }
        game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sHous1e"):FireServer(unpack(args))
print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Fogo On",
   Description = "Very important button",
   Callback = function()
      local args = {
            [1] = "PlayerWantsFireOnFirePassNotShowingAnyone"
        }
        game:GetService("ReplicatedStorage").RE:FindFirstChild("1Player1sHous1e"):FireServer(unpack(args))
 print("Clicked!")
   end
})


Tab:AddParagraph({
    Title = "<Perm House>",
    Content = ""
})


local casaNumbers = {}
for i = 1, 35 do
if i ~= 8 and i ~= 9 and i ~= 10 then
table.insert(casaNumbers, tostring(i))
end
end

local selectedCasaNumber = nil

local Dropdown = Tab:AddDropdown("Dropdown", {
    Title = "Escolha o número da casa",
    Values = casaNumbers,
    Multi = false,
    Default = 1,
})

Dropdown:OnChanged(function(number)
    selectedCasaNumber = tonumber(number)
end)


Tab:AddButton({
   Title = "Pega Permissão",
   Description = "Very important button",
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
 print("Clicked!")
   end
})


local Tab = Window:AddTab({ Title = "Audio Fe", Icon = "radio" })


Tab:AddParagraph({
    Title = "<Bombox Tool>",
    Content = ""
})


Tab:AddButton({
   Title = "Bombox Sem Gamepass",
   Description = "Very important button",
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
print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Bombox(Requer Game pass)",
   Description = "Very important button",
   Callback = function()
       local player = game.Players.LocalPlayer

-- Função que será executada após o renascimento
local function onCharacterAdded(character)
    -- Aguarda o personagem carregar completamente
    character:WaitForChild("HumanoidRootPart")

    -- Executa a sequência de comandos após renascer
    local args = {
        [1] = "CharacterSizeDown",
        [2] = 4
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clothe1s"):FireServer(unpack(args))
    wait(0.1)

    local args = {
        [1] = "SkateBoard"
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
    wait(0.1)

    local args = {
        [1] = "CharacterSizeUp",
        [2] = 1
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clothe1s"):FireServer(unpack(args))
end

-- Conecta a função ao evento CharacterAdded
player.CharacterAdded:Connect(onCharacterAdded)

-- Caso o jogador já tenha um personagem no momento do script ser executado
if player.Character then
    onCharacterAdded(player.Character)
end
wait(0.1)
-- Criar a Tool
local player = game.Players.LocalPlayer
local backpack = player:WaitForChild("Backpack")

local tool = Instance.new("Tool")
tool.Name = "BoomBox"
tool.RequiresHandle = true
tool.Parent = backpack
tool.TextureId = "rbxassetid://135246786635323"

-- Criar a Handle invisível
local handle = Instance.new("Part")
handle.Name = "Handle"
handle.Size = Vector3.new(1, 1, 1)
handle.Transparency = 1
handle.CanCollide = false
handle.Anchored = false
handle.Parent = tool

-- Função para enviar comandos
local function sendUpdateAvatar()
    local args = {
        [1] = "wear",
        [2] = 18756289999
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r"):FireServer(unpack(args))
end

local function sendPickingScooterMusicText(id)
    local args = {
        [1] = "PickingScooterMusicText",
        [2] = id
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
end

local function sendPickingScooterMusicStop()
    local args = {
        [1] = "PickingScooterMusicStop"
    }
    game:GetService("ReplicatedStorage").RE:FindFirstChild("1NoMoto1rVehicle1s"):FireServer(unpack(args))
end

-- Variável para armazenar o menu do Boombox
local boomboxMenu

-- Menu do Boombox
local function createMenu()
    boomboxMenu = Instance.new("ScreenGui", player:WaitForChild("PlayerGui"))
    local frame = Instance.new("Frame", boomboxMenu)
    frame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
    frame.BackgroundTransparency = 0.5
    frame.Size = UDim2.new(0.3, 0, 0.3, 0)
    frame.Position = UDim2.new(0.35, 0, 0.35, 0)
    frame.BorderSizePixel = 0
    frame.ClipsDescendants = true

    local title = Instance.new("TextLabel", frame)
    title.Text = "Boombox Menu"
    title.Font = Enum.Font.GothamBold
    title.TextSize = 24
    title.Size = UDim2.new(1, 0, 0.2, 0)
    title.BackgroundTransparency = 1
    title.TextColor3 = Color3.fromRGB(255, 255, 255)

    local textBox = Instance.new("TextBox", frame)
    textBox.Size = UDim2.new(0.8, 0, 0.1, 0)
    textBox.Position = UDim2.new(0.1, 0, 0.25, 0)
    textBox.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
    textBox.BackgroundTransparency = 0.5
    textBox.TextColor3 = Color3.fromRGB(255, 255, 255)
    textBox.BorderSizePixel = 0
    textBox.Text = ""

    local submitButton = Instance.new("TextButton", frame)
    submitButton.Size = UDim2.new(0.8, 0, 0.1, 0)
    submitButton.Position = UDim2.new(0.1, 0, 0.4, 0)
    submitButton.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
    submitButton.BackgroundTransparency = 0.5
    submitButton.Text = "Tocar Áudio"
    submitButton.TextColor3 = Color3.fromRGB(255, 255, 255)
    submitButton.BorderSizePixel = 0

    local stopButton = Instance.new("TextButton", frame)
    stopButton.Size = UDim2.new(0.8, 0, 0.1, 0)
    stopButton.Position = UDim2.new(0.1, 0, 0.55, 0) -- Abaixo do botão Tocar Áudio
    stopButton.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
    stopButton.BackgroundTransparency = 0.5
    stopButton.Text = "Parar Áudio"
    stopButton.TextColor3 = Color3.fromRGB(255, 255, 255)
    stopButton.BorderSizePixel = 0

    local closeButton = Instance.new("TextButton", frame)
    closeButton.Size = UDim2.new(0.1, 0, 0.1, 0)
    closeButton.Position = UDim2.new(0.9, 0, 0, 0)
    closeButton.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
    closeButton.BackgroundTransparency = 0.5
    closeButton.Text = "X"
    closeButton.TextColor3 = Color3.fromRGB(255, 255, 255)
    closeButton.BorderSizePixel = 0

    closeButton.MouseButton1Click:Connect(function()
        boomboxMenu:Destroy() -- Destrói o menu ao clicar no botão "X"
        boomboxMenu = nil -- Limpa a referência
    end)

    submitButton.MouseButton1Click:Connect(function()
        local inputId = textBox.Text
        if tonumber(inputId) then
            sendPickingScooterMusicText(inputId)
        else
            print("Por favor, insira um número válido.")
        end
    end)

    stopButton.MouseButton1Click:Connect(function()
        sendPickingScooterMusicStop() -- Chama a função para parar o áudio
    end)
end

-- Função para alternar entre abrir e fechar o menu do Boombox
local function toggleMenu()
    if boomboxMenu then
        boomboxMenu:Destroy() -- Se o menu já existe, destrua-o
        boomboxMenu = nil -- Limpa a referência
    else
        createMenu() -- Se o menu não existe, crie-o
    end
end

-- Criar botão para abrir o menu do Boombox
local function createOpenButton()
    local screenGui = Instance.new("ScreenGui", player:WaitForChild("PlayerGui"))
    local openButton = Instance.new("TextButton", screenGui)
    openButton.Size = UDim2.new(0, 50, 0, 50)  -- Tamanho quadrado
    openButton.Position = UDim2.new(0.01, 0, 0.01, 0)  -- Canto superior esquerdo
    openButton.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
    openButton.BackgroundTransparency = 0.5
    openButton.BorderSizePixel = 0
    openButton.Text = ""
    openButton.AutoButtonColor = false
    openButton.AnchorPoint = Vector2.new(0, 0) -- Garante que o botão fique no canto

    -- Bordas arredondadas
    local corner = Instance.new("UICorner", openButton)
    corner.CornerRadius = UDim.new(0.25, 0) -- Borda arredondada

    local imageLabel = Instance.new("ImageLabel", openButton)
    imageLabel.Size = UDim2.new(1, 0, 1, 0)
    imageLabel.Image = "rbxassetid://135246786635323"
    imageLabel.BackgroundTransparency = 1

    openButton.MouseButton1Click:Connect(function()
        toggleMenu() -- Alterna entre abrir e fechar o menu do Boombox
    end)

    return openButton
end

local openButton -- Variável para armazenar o botão

-- Conectar funções de equipar e desequipar
tool.Equipped:Connect(function()
    sendUpdateAvatar()
    openButton = createOpenButton() -- Cria o botão quando a ferramenta é equipada
end)

tool.Unequipped:Connect(function()
    sendUpdateAvatar()
    sendPickingScooterMusicStop() -- Para o áudio ao desequipar a ferramenta
    if openButton then
        openButton.Parent:Destroy() -- Remove o botão quando a ferramenta é desequipada
        openButton = nil
    end
    if boomboxMenu then
        boomboxMenu:Destroy() -- Remove o menu do Boombox quando a ferramenta é desequipada
        boomboxMenu = nil -- Limpa a referência
    end
end)

print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Loop sound all-Safe",
   Description = "Very important button",
   Callback = function()
       -- Cria uma parte invisÃ­vel e sem colisÃ£o
local parte = Instance.new("Part")
parte.Size = Vector3.new(1, 1, 1) -- Tamanho mÃ­nimo
parte.Position = Vector3.new(0, 10000, 999)
parte.Anchored = true
parte.CanCollide = false
parte.Transparency = 1  -- InvisÃ­vel
parte.Parent = game.Workspace

-- Cria o som
local som = Instance.new("Sound")
som.SoundId = "rbxassetid://7236490488"  -- Substitua pelo ID do seu arquivo de som
som.Parent = parte
som.Volume = 999  -- Volume mÃ¡ximo
som.MaxDistance = 99999999999999999999999999999999999  -- DistÃ¢ncia mÃ¡xima de reproduÃ§Ã£o do som
som.RollOffMode = Enum.RollOffMode.Linear -- Som se extingue linearmente com a distÃ¢ncia

-- FunÃ§Ã£o para tocar o som
local function tocarSom()
    som:Play()
end

-- Toca o som
tocarSom()

-- Opcional: Repetir a mÃºsica apÃ³s acabar
som.Ended:Connect(function()
    tocarSom()  -- Rechama a funÃ§Ã£o para tocar o som novamente
end)
print("Clicked!")
   end
})


local Tab = Window:AddTab({ Title = "All Player", Icon = "person-standing" })


Tab:AddButton({
   Title = "Fling all",
   Description = "Very important button",
   Callback = function()
      local Targets = {"All"} -- "All", "Target Name", "arian_was_here"

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
    game:GetService("StarterGui"):SetCore("SendNotification", {Title = _Title, Text = _Text, Duration = Time})
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
            return Message("Error Occurred", "Targeting is sitting", 5) -- u can remove dis part if u want lol
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
            return Message("Error Occurred", "Target is missing everything", 5)
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
        return Message("Error Occurred", "Random error", 5)
    end
end

if not Welcome then Message("Script by AnthonyIsntHere", "Enjoy!", 5) end
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
            Message("Error Occurred", "This user is whitelisted! (Owner)", 5)
        end
    elseif not GetPlayer(x) and not AllBool then
        Message("Error Occurred", "Username Invalid", 5)
    end
end
 print("Clicked!")
   end
})


-- Variável para controlar o toggle
local teleportToggle = false

-- Função de teletransporte
local function teleportToPlayers()
    local localPlayer = game.Players.LocalPlayer
    local players = game.Players:GetPlayers()
    
    for _, player in pairs(players) do
        if not teleportToggle then break end -- Para se o toggle for desativado
        if player ~= localPlayer then
        --Ficar pequeno antes
        local args = {
[1] = "CharacterSizeDown",
[2] = 5
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clothe1s"):FireServer(unpack(args))
            -- Teleporta para o jogador
            local character = player.Character
            if character and character:FindFirstChild("HumanoidRootPart") then
                local hrp = character.HumanoidRootPart
                localPlayer.Character.HumanoidRootPart.CFrame = hrp.CFrame
                wait(1) -- Aguarda 1 segundo para evitar problemas de sincronia
            end
        end
        -- Teleporta para (-8.657157897949219, -222.3133087158203, -23.58349609375)
        localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-8.657157897949219, -222.3133087158203, -23.58349609375)
        wait(1) -- Aguarda antes de passar para o próximo jogador
    end
end



local Toggle = Tab:AddToggle("MyToggle", {Title = "Kill All", Default = false })

Toggle:OnChanged(function(state)
    teleportToggle = state
        if teleportToggle then
            teleportToPlayers(state)
        end
end)



-- Variável para controlar o toggle
local teleportToggle = false

-- Função de teletransporte
local function teleportToSky()


--xaet

local args = {
[1] = "PickingTools",
[2] = "ShoppingCart"
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

--xaetttttt

local args = {
[1] = "PickingTools",
[2] = "Stretcher"
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

--Couch

local args = {
[1] = "PickingTools",
[2] = "Couch"
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1Too1l"):InvokeServer(unpack(args))

--Equip itens

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
equiparItem("Couch")
equiparItem("ShoppingCart")
equiparItem("Stretcher")

    local localPlayer = game.Players.LocalPlayer
    local players = game.Players:GetPlayers()
    
    for _, player in pairs(players) do
        if not teleportToggle then break end -- Para se o toggle for desativado
        if player ~= localPlayer then
        --Ficar pequeno antes
        local args = {
[1] = "CharacterSizeDown",
[2] = 5
}
game:GetService("ReplicatedStorage").RE:FindFirstChild("1Clothe1s"):FireServer(unpack(args))
            -- Teleporta para o jogador
            local character = player.Character
            if character and character:FindFirstChild("HumanoidRootPart") then
                local hrp = character.HumanoidRootPart
                localPlayer.Character.HumanoidRootPart.CFrame = hrp.CFrame
                wait(1) -- Aguarda 1 segundo para evitar problemas de sincronia
            end
        end
        -- Teleporta para (9999999827968, 9999999827968, 9999999827968)
        localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(9999999827968, 9999999827968, 9999999827968)
        wait(1) -- Aguarda antes de passar para o próximo jogador
    end
end


local Toggle = Tab:AddToggle("MyToggle", {Title = "Bug all", Default = false })

Toggle:OnChanged(function(state)
    teleportToggle = state
        if teleportToggle then
            teleportToSky(state)
        end
end)


-- Variáveis e serviços
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer
local TeleportToggle = false
local OriginalPosition

-- Função para teletransportar e voltar à posição original
local function TeleportToPlayers()
    while TeleportToggle do
        -- Salva a posição original do jogador
        if not OriginalPosition then
            OriginalPosition = LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("HumanoidRootPart").CFrame
        end
        
        for _, player in ipairs(Players:GetPlayers()) do
            -- Ignora o jogador local
            if player ~= LocalPlayer and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
                -- Teleporta para o jogador
                LocalPlayer.Character.HumanoidRootPart.CFrame = player.Character.HumanoidRootPart.CFrame
                wait(1) -- Espera 1 segundo antes de ir para o próximo jogador
                
                -- Retorna para a posição original
                if OriginalPosition then
                    LocalPlayer.Character.HumanoidRootPart.CFrame = OriginalPosition
                end
                wait(1) -- Espera 1 segundo antes de continuar
            end
        end
        
        -- Reseta a posição original se todos foram visitados
        OriginalPosition = nil
    end
end



local Toggle = Tab:AddToggle("MyToggle", {Title = "Bring all", Default = false })

Toggle:OnChanged(function(state)
    TeleportToggle = state
        if TeleportToggle then
            TeleportToPlayers(state)
        end
end)


local Tab = Window:AddTab({ Title = "Raid", Icon = "activity" })


Tab:AddButton({
   Title = "Spam Caminhão",
   Description = "Very important button",
   Callback = function()
       local args = {
            [1] = "PickingCar",
            [2] = "Semi"
        }
        game:GetService("ReplicatedStorage").RE:FindFirstChild("1Ca1r"):FireServer(unpack(args))
print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Aplica título no caminhão-Police Brookhaven Raid",
   Description = "Very important button",
   Callback = function()
       local args = {
			[1] = "ReturningSemiName",
			[2] = "Police Brookhaven Raid"
		}
		game:GetService("ReplicatedStorage").RE:FindFirstChild("1Cemeter1y"):FireServer(unpack(args))
print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Tool black Role",
   Description = "Very important button",
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
print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Tool  Telekiness",
   Description = "Very important button",
   Callback = function()
     loadstring(game:HttpGet(('https://raw.githubusercontent.com/SAZXHUB/Control-update/main/README.md'),true))()
  print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Black Role gui V1",
   Description = "Very important button",
   Callback = function()
    loadstring(game:HttpGet("https://pastefy.app/pYhER1z4/raw"))()
   print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Black Role gui V2",
   Description = "Very important button",
   Callback = function()
       loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Fe-blackhole-re-upload-18510"))()
print("Clicked!")
   end
})


local Tab = Window:AddTab({ Title = "Esp", Icon = "eye" })


local toggles = {
    EspVermelho = false
}

local function activateHighlight()
    local FillColor = Color3.fromRGB(14, 10, 255)
    local DepthMode = "AlwaysOnTop"
    local FillTransparency = 0.5
    local OutlineColor = Color3.fromRGB(14, 10, 255)
    local OutlineTransparency = 0

    local CoreGui = game:FindService("CoreGui")
    local Players = game:FindService("Players")
    local lp = Players.LocalPlayer
    local connections = {}

    local Storage = Instance.new("Folder")
    Storage.Parent = CoreGui
    Storage.Name = "Highlight_Storage"

    local function Highlight(plr)
        local Highlight = Instance.new("Highlight")
        Highlight.Name = plr.Name
        Highlight.FillColor = FillColor
        Highlight.DepthMode = DepthMode
        Highlight.FillTransparency = FillTransparency
        Highlight.OutlineColor = OutlineColor
        Highlight.OutlineTransparency = OutlineTransparency
        Highlight.Parent = Storage

        local plrchar = plr.Character
        if plrchar then
            Highlight.Adornee = plrchar
        end

        connections[plr] = plr.CharacterAdded:Connect(function(char)
            Highlight.Adornee = char
        end)
    end

    Players.PlayerAdded:Connect(Highlight)
    for _, v in next, Players:GetPlayers() do
        Highlight(v)
    end

    Players.PlayerRemoving:Connect(function(plr)
        local plrname = plr.Name
        if Storage:FindFirstChild(plrname) then
            Storage[plrname]:Destroy()
        end
        if connections[plr] then
            connections[plr]:Disconnect()
        end
    end)

    return function()
        if Storage then
            Storage:Destroy()
        end
        for _, conn in pairs(connections) do
            conn:Disconnect()
        end
        connections = {}
    end
end

local deactivateHighlight


local Toggle = Tab:AddToggle("MyToggle", {Title = "Esp Azul", Default = false })

Toggle:OnChanged(function(state)
    toggles.EspVermelho = state
        if state then
            deactivateHighlight = activateHighlight()
        elseif deactivateHighlight then
            deactivateHighlight()
            deactivateHighlight = nil
        end
end)


Tab:AddParagraph({
    Title = "Esp Ver idade da contas Do jogadores+detect Ant sit ",
    Content = ""
})


local toggles = {
    EspIdadeDaConta = false
}

local connections = {}
local function createESP(player)
    if not player.Character or not player.Character:FindFirstChild("Head") then return end

    -- Criar um BillboardGui para mostrar os dias da conta
    local billboardGui = Instance.new("BillboardGui")
    billboardGui.Name = "AccountAgeESP"
    billboardGui.Adornee = player.Character:FindFirstChild("Head")
    billboardGui.Size = UDim2.new(0, 200, 0, 50)
    billboardGui.StudsOffset = Vector3.new(0, 3, 0)
    billboardGui.AlwaysOnTop = true
    
    -- Criar um Label para exibir os dias da conta
    local textLabel = Instance.new("TextLabel")
    textLabel.Parent = billboardGui
    textLabel.Size = UDim2.new(1, 0, 1, 0)
    textLabel.Text = "Dias da conta: " .. tostring(player.AccountAge)
    textLabel.TextColor3 = Color3.new(1, 1, 1)
    textLabel.BackgroundTransparency = 1
    textLabel.Font = Enum.Font.SourceSansBold
    textLabel.TextSize = 14

    -- Adicionar o BillboardGui à cabeça do jogador
    billboardGui.Parent = player.Character:FindFirstChild("Head")
end

local function removeESP(player)
    if player.Character and player.Character:FindFirstChild("Head") then
        local head = player.Character:FindFirstChild("Head")
        local esp = head:FindFirstChild("AccountAgeESP")
        if esp then
            esp:Destroy()
        end
    end
end

local function enableESP()
    -- Adicionar ESP para todos os jogadores no jogo
    for _, player in pairs(game.Players:GetPlayers()) do
        if player.Character and player.Character:FindFirstChild("Head") then
            createESP(player)
        end
    end

    -- Adicionar ESP para novos jogadores que entram no jogo
    connections.PlayerAdded = game.Players.PlayerAdded:Connect(function(player)
        connections[player] = player.CharacterAdded:Connect(function()
            wait(1) -- Espera para garantir que o personagem foi carregado
            if player.Character and player.Character:FindFirstChild("Head") then
                createESP(player)
            end
        end)
    end)

    -- Remover ESP quando o jogador sai
    connections.PlayerRemoving = game.Players.PlayerRemoving:Connect(function(player)
        removeESP(player)
        if connections[player] then
            connections[player]:Disconnect()
            connections[player] = nil
        end
    end)
end

local function disableESP()
    for _, player in pairs(game.Players:GetPlayers()) do
        removeESP(player)
    end

    -- Desconectar todos os eventos
    for _, conn in pairs(connections) do
        if conn then
            conn:Disconnect()
        end
    end
    connections = {}
end


local Toggle = Tab:AddToggle("MyToggle", {Title = "Ativa Esp da idade da conta", Default = false })

Toggle:OnChanged(function(state)
    toggles.EspIdadeDaConta = state
        if state then
            enableESP()
        else
            disableESP()
        end
end)


local toggles = {
    EspToggle = false
}

local function createESP(player)
    if not player.Character or not player.Character:FindFirstChild("HumanoidRootPart") then return end

    local espLabel = Instance.new("BillboardGui")
    espLabel.Name = "ESPLabel"
    espLabel.Adornee = player.Character:FindFirstChild("HumanoidRootPart")
    espLabel.Size = UDim2.new(0, 100, 0, 50)
    espLabel.AlwaysOnTop = true
    espLabel.StudsOffset = Vector3.new(0, 2, 0)
    espLabel.Parent = player.Character:FindFirstChild("HumanoidRootPart")

    local textLabel = Instance.new("TextLabel")
    textLabel.Parent = espLabel
    textLabel.Size = UDim2.new(1, 0, 1, 0)
    textLabel.BackgroundTransparency = 1
    textLabel.TextColor3 = Color3.new(1, 1, 1)
    textLabel.TextScaled = true
    textLabel.TextWrapped = true -- Ajustar tamanho do texto

    local function updateLabel(status)
        textLabel.Text = player.Name .. " - stats: " .. status
    end

    local function updateESP()
        local status = "normal"
        local color = Color3.new(0, 1, 0)
        if player.Character.Humanoid.Sit then
            status = "Sitting"
            color = Color3.new(0, 1, 1)
        elseif player.Character:FindFirstChild("noclip") then
            status = "noclipando"
            color = Color3.new(0.5, 0.25, 0)
        end
        for _, part in pairs(player.Character:GetChildren()) do
            if part:IsA("BasePart") then
                local espBox = part:FindFirstChild("ESP")
                if not espBox then
                    espBox = Instance.new("BoxHandleAdornment")
                    espBox.Name = "ESP"
                    espBox.Adornee = part
                    espBox.Size = part.Size
                    espBox.Transparency = 0.5
                    espBox.AlwaysOnTop = true
                    espBox.ZIndex = 10
                    espBox.Parent = part
                end
                espBox.Color3 = color
            end
        end
        updateLabel(status)
    end

    updateESP()
    
    player.Character.Humanoid:GetPropertyChangedSignal("Sit"):Connect(updateESP)
    player.Character.Humanoid.StateChanged:Connect(updateESP)
    player.Character.HumanoidRootPart:GetPropertyChangedSignal("Velocity"):Connect(updateESP)
    player.Character.ChildAdded:Connect(function(child)
        if child.Name == "noclip" then
            updateESP()
        end
    end)
end

local function activateESP()
    for _, player in pairs(game.Players:GetPlayers()) do
        if player ~= game.Players.LocalPlayer then
            createESP(player)
        end
    end
    game.Players.PlayerAdded:Connect(function(player)
        player.CharacterAdded:Connect(function()
            wait(1)
            if toggles.EspToggle and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
                createESP(player)
            end
        end)
    end)
end

local function deactivateESP()
    for _, player in pairs(game.Players:GetPlayers()) do
        if player.Character and player.Character:FindFirstChild("HumanoidRootPart") and player.Character.HumanoidRootPart:FindFirstChild("ESPLabel") then
            player.Character.HumanoidRootPart.ESPLabel:Destroy()
        end
        for _, part in pairs(player.Character:GetChildren()) do
            if part:IsA("BasePart") and part:FindFirstChild("ESP") then
                part.ESP:Destroy()
            end
        end
    end
end


local Toggle = Tab:AddToggle("MyToggle", {Title = "ativa detection Ant sit By:The mr red Black", Default = false })

Toggle:OnChanged(function(state)
    toggles.EspToggle = state
        if state then
            activateESP()
        else
            deactivateESP()
        end
end)


local Tab = Window:AddTab({ Title = "Teleports", Icon = "map" })

Tab:AddButton({
   Title = "Lobby",
   Description = "Very important button",
   Callback = function()
     local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(7.159717559814453, 3.3000009059906006, 19.785301208496094)
  print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Wather",
   Description = "Very important button",
   Callback = function()
local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(-72.37123107910156, -10.816083908081055, 112.93341827392578)
       print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Edge",
   Description = "Very important button",
   Callback = function()
     local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(-1354.4154052734375, 76.11813354492188, -1278.5859375)
  print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Void",
   Description = "Very important button",
   Callback = function()
  local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(9999999827968, 9999999827968, 9999999827968)
     print("Clicked!")
   end
})



Tab:AddButton({
   Title = "Commercial 1",
   Description = "Very important button",
   Callback = function()
       local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(-242.68215942382812, 89.68680572509766, -549.6495361328125)
print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Commercial 2",
   Description = "Very important button",
   Callback = function()
     local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(-630.480712890625, 26.586822509765625, 365.14093017578125)
  print("Clicked!")
   end
})



Tab:AddButton({
   Title = "Secret 1",
   Description = "Very important button",
   Callback = function()
 local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(223.24264526367188, -37.5954704284668, -153.50656127929688)
      print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Secret 2",
   Description = "Very important button",
   Callback = function()
   local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(-350.3148498535156, 45.385169982910156, -123.7399673461914)
    print("Clicked!")
   end
})



Tab:AddButton({
   Title = "Secret 3",
   Description = "Very important button",
   Callback = function()
  local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(-271.9717712402344, 22.992469787597656, 1115.3104248046875)
     print("Clicked!")
   end
})



Tab:AddButton({
   Title = "Secret 4",
   Description = "Very important button",
   Callback = function()
      local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(-35.98054122924805, -48.27098083496094, 220.8909912109375)
  print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Secret 5",
   Description = "Very important button",
   Callback = function()
 local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(15.010516166687012, -29.14361000061035, -60.09798812866211)
      print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Bow 1",
   Description = "Very important button",
   Callback = function()
      local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(-589.1044311523438, 140.25389099121094, -60.75751876831055)
 print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Bow 2",
   Description = "Very important button",
   Callback = function()
   local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(624.4569702148438, 133.63233947753906, -59.50937271118164)
    print("Clicked!")
   end
})


Tab:AddButton({
   Title = "School",
   Description = "Very important button",
   Callback = function()
       local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(-288.21392822265625, 4.142392635345459, 212.0995635986328)
print("Clicked!")
   end
})



Tab:AddButton({
   Title = "Hospital",
   Description = "Very important button",
   Callback = function()
     local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(-306.9185485839844, 4.1286420822143555, 7.26304817199707)
  print("Clicked!")
   end
})


Tab:AddButton({
   Title = "Plane",
   Description = "Very important button",
   Callback = function()
   local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(450.3541564941406, -106.24927520751953, 112.56250762939453)
    print("Clicked!")
   end
})



Tab:AddButton({
   Title = "Police state",
   Description = "Very important button",
   Callback = function()
   local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(-118.54170227050781, 3.8526408672332764, -1.622152805328369)
    print("Clicked!")
   end
})



Tab:AddButton({
   Title = "Cinema",
   Description = "Very important button",
   Callback = function()
    local plr = game.Players.LocalPlayer
local char = plr.Character
local hrp = char.HumanoidRootPart

hrp.CFrame = CFrame.new(190.19032287597656, -26.225231170654297, -184.5957489013672)
   print("Clicked!")
   end
})
