local player = game.Players.LocalPlayer
local azuls = game.Teams.Blue
local vermelho = game.Teams.Red

while true do
    local character = player.Character or player.CharacterAdded:Wait()
    local hrp = character:WaitForChild("HumanoidRootPart")

    if player.Team == azuls then
        hrp.CFrame = CFrame.new(-56, 9.80356979, 170)
        task.wait(2)
        hrp.CFrame = CFrame.new(-35, 8.00001144, 111)

    elseif player.Team == vermelho then
        hrp.CFrame = CFrame.new(-56, 9.80356979, -176)
        task.wait(2)
        hrp.CFrame = CFrame.new(-75, 8.00001144, -117)

    else
        print("O jogador não está em nenhum desses times.")
    end

    task.wait(0.1)
end
