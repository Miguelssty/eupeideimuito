local player = game.Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")
local screenGui = Instance.new("ScreenGui")
screenGui.Parent = playerGui

local frame = Instance.new("Frame")
frame.Parent = screenGui

frame.Size = UDim2.new(0,300,0,200)
frame.Position = UDim2.new(0.5,-150,0.5,-100)
frame.Active = true
frame.Draggable = true

local botao = Instance.new("TextButton")
botao.Parent = frame

botao.Size = UDim2.new(0, 120, 0, 40)
botao.Position = UDim2.new(0.5, -60, 0.5, -40)
botao.Text = "Start farming."

botao.MouseButton1Click:Connect(function()
local azuls = game.Teams.Blue
local vermelho = game.Teams.Red

while true do
    local character = player.Character or player.CharacterAdded:Wait()
    local hrp = character:WaitForChild("HumanoidRootPart")

    if player.Team == azuls then
        hrp.CFrame = CFrame.new(-56, 9.80356979, 170)
        task.wait(0.1)
        hrp.CFrame = CFrame.new(-35, 8.00001144, 111)

    elseif player.Team == vermelho then
        hrp.CFrame = CFrame.new(-56, 9.80356979, -176)
        task.wait(0.1)
        hrp.CFrame = CFrame.new(-75, 8.00001144, -117)

    else
        print("O jogador não está em nenhum desses times.")
    end

    task.wait(0.1)
end
end)
