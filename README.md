local speedEnabled = false

local speedValue = 100 -- Cambiá este número si querés ir más rápido o más lento

-- Función para alternar velocidad

function toggleSpeed()

    speedEnabled = not speedEnabled

    local player = game.Players.LocalPlayer

    local humanoid = player.Character and player.Character:FindFirstChildOfClass("Humanoid")

    if humanoid then

        if speedEnabled then

            humanoid.WalkSpeed = speedValue

            print("Velocidad activada")

        else

            humanoid.WalkSpeed = 16 -- Velocidad por defecto

            print("Velocidad desactivada")

        end

    end

end

-- Tecla para alternar velocidad (tecla "F")

game:GetService("UserInputService").InputBegan:Connect(function(input, gameProcessed)

    if not gameProcessed and input.KeyCode == Enum.KeyCode.F then

        toggleSpeed()

    end

end)

print("Script de velocidad cargado. Presioná F para activar/desactivar.")
