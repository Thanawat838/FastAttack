getgenv().FastAttack = true
getgenv().UserFastAttack = true
    
local CombatFrameworkROld = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework) 
local CombatFrameworkR = getupvalues(CombatFrameworkROld)[2]
local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
CameraShakerR:Stop()
function Attack()
    local CombatFrameworkROld = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework) 
    local CombatFrameworkR = getupvalues(CombatFrameworkROld)[2]
    if CombatFrameworkR.activeController:Attack() then
        CombatFrameworkR.activeController:Attack()
    end
end
spawn(function()
    game:GetService("RunService").Heartbeat:Connect(function()
        pcall(function()
            CombatFrameworkR.activeController.hitboxMagnitude = 55
            if getgenv().UserFastAttack then
                if getgenv().FastAttack then
                    Attack() Attack() Attack()
                    CombatFrameworkR.activeController.increment = 3
                    CombatFrameworkR.activeController.blocking = false
                    game.Players.LocalPlayer.Character.Humanoid.Sit = false
                end
            end
        end)
        task.wait()
    end)
end)
spawn(function()
    game:GetService("RunService").Heartbeat:Connect(function()
        pcall(function()
            CombatFrameworkR.activeController.hitboxMagnitude = 55
            if getgenv().UserFastAttack then
                if getgenv().FastAttack then
                    Attack() Attack() Attack()
                    CombatFrameworkR.activeController.increment = 3
                    CombatFrameworkR.activeController.blocking = false
                    game.Players.LocalPlayer.Character.Humanoid.Sit = false
                end
            end
        end)
        task.wait()
    end)
end)
