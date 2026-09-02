--==================================================
-- VFX ANIMS
-- Roblox Animation Pack Selector
--==================================================

local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")

local player = Players.LocalPlayer

--==================================================
-- OFFICIAL ROBLOX ANIMATION PACKS
--==================================================

local Packs = {

	Astronaut = {
		Run = 891636393,
		Walk = 891636393,
		Jump = 891627522,
		Idle1 = 891621366,
		Idle2 = 891633237,
		Fall = 1047759695,
		Swim = 891617961,
		SwimIdle = 891639666,
		Climb = 891663592,
	},

	Bubbly = {
		Run = 910025107,
		Walk = 910034870,
		Jump = 910016857,
		Idle1 = 910004836,
		Idle2 = 910009958,
		Fall = 1018536639,
		Swim = 910001910,
		SwimIdle = 910028158,
		Climb = 910030921,
	},

	Cartoony = {
		Run = 742638842,
		Walk = 742640026,
		Jump = 742637942,
		Idle1 = 742637544,
		Idle2 = 742638445,
		Fall = 885477856,
		Swim = 742637151,
		SwimIdle = 742639220,
		Climb = 742639812,
	},

	Elder = {
		Run = 845386501,
		Walk = 845403856,
		Jump = 845398858,
		Idle1 = 845397899,
		Idle2 = 845400520,
		Fall = 901160519,
		Swim = 845396048,
		SwimIdle = 845401742,
		Climb = 845403127,
	},

	Knight = {
		Run = 657564596,
		Walk = 657552124,
		Jump = 658409194,
		Idle1 = 657595757,
		Idle2 = 657568135,
		Fall = 885499184,
		Swim = 657600338,
		SwimIdle = 657560551,
		Climb = 657557095,
	},

	Levitation = {
		Run = 616010382,
		Walk = 616013216,
		Jump = 616008936,
		Idle1 = 616006778,
		Idle2 = 616008087,
		Fall = 886862142,
		Swim = 616005863,
		SwimIdle = 616011509,
		Climb = 616012453,
	},

	Mage = {
		Run = 707861613,
		Walk = 707897309,
		Jump = 707853694,
		Idle1 = 707742142,
		Idle2 = 707855907,
		Fall = 885508740,
		Swim = 707829716,
		SwimIdle = 707876443,
		Climb = 707894699,
	},

	Ninja = {
		Run = 656118852,
		Walk = 656121766,
		Jump = 656117878,
		Idle1 = 656117400,
		Idle2 = 656118341,
		Fall = 886742569,
		Swim = 656115606,
		SwimIdle = 656119721,
		Climb = 656121397,
	},

	Pirate = {
		Run = 750783738,
		Walk = 750785693,
		Jump = 750782230,
		Idle1 = 750781874,
		Idle2 = 750782770,
		Fall = 885515365,
		Swim = 750780242,
		SwimIdle = 750784579,
		Climb = 750785176,
	},

	Robot = {
		Run = 616091570,
		Walk = 616095330,
		Jump = 616090535,
		Idle1 = 616088211,
		Idle2 = 616089559,
		Fall = 885531463,
		Swim = 616087089,
		SwimIdle = 616092998,
		Climb = 616094091,
	},

	Rthro = {
		Run = 2510198475,
		Walk = 2510202577,
		Jump = 2510197830,
		Idle1 = 2510197257,
		Idle2 = 2510196951,
		Fall = 3711062489,
		Swim = 2510195892,
		SwimIdle = 2510199791,
		Climb = 2510201162,
	},

	Stylish = {
		Run = 616140816,
		Walk = 616146177,
		Jump = 616139451,
		Idle1 = 616136790,
		Idle2 = 616138447,
		Fall = 886888594,
		Swim = 616134815,
		SwimIdle = 616143378,
		Climb = 616144772,
	},

	Superhero = {
		Run = 616117076,
		Walk = 616122287,
		Jump = 616115533,
		Idle1 = 616111295,
		Idle2 = 616113536,
		Fall = 885535855,
		Swim = 616108001,
		SwimIdle = 616119360,
		Climb = 616120861,
	},

	Toy = {
		Run = 782842708,
		Walk = 782843345,
		Jump = 782847020,
		Idle1 = 782841498,
		Idle2 = 782845736,
		Fall = 980952228,
		Swim = 782846423,
		SwimIdle = 782844582,
		Climb = 782845186,
	},

	Vampire = {
		Run = 1083462077,
		Walk = 1083473930,
		Jump = 1083455352,
		Idle1 = 1083445855,
		Idle2 = 1083450166,
		Fall = 1088037547,
		Swim = 1083443587,
		SwimIdle = 1083464683,
		Climb = 1083467779,
	},

	Werewolf = {
		Run = 1083216690,
		Walk = 1083178339,
		Jump = 1083218792,
		Idle1 = 1083195517,
		Idle2 = 1083214717,
		Fall = 1099492820,
		Swim = 1083189019,
		SwimIdle = 1083222527,
		Climb = 1083225406,
	},

	Zombie = {
		Run = 616163682,
		Walk = 616168032,
		Jump = 616161997,
		Idle1 = 616158929,
		Idle2 = 616160636,
		Fall = 885545458,
		Swim = 616157476,
		SwimIdle = 616165109,
		Climb = 616156119,
	},
}

--==================================================
-- ORDER
--==================================================

local PackNames = {
	"Astronaut",
	"Bubbly",
	"Cartoony",
	"Elder",
	"Knight",
	"Levitation",
	"Mage",
	"Ninja",
	"Pirate",
	"Robot",
	"Rthro",
	"Stylish",
	"Superhero",
	"Toy",
	"Vampire",
	"Werewolf",
	"Zombie",
}

local AnimationNames = {
	"Run",
	"Walk",
	"Jump",
	"Idle 1",
	"Idle 2",
	"Fall",
	"Swim",
	"Swim Idle",
	"Climb",
}

--==================================================
-- STATE
--==================================================

local selectedPack = "Vampire"
local selectedAnimation = "Walk"
local currentAppliedPack = nil

local menuOpen = true
local dropdownOpen = nil

--==================================================
-- CHARACTER
--==================================================

local function getCharacter()
	return player.Character
end

local function getAnimate()
	local character = getCharacter()

	if not character then
		return nil
	end

	local humanoid = character:FindFirstChildOfClass("Humanoid")

	if not humanoid then
		return nil
	end

	if humanoid.RigType ~= Enum.HumanoidRigType.R15 then
		warn("VFX Anims requires an R15 character.")
		return nil
	end

	return character:FindFirstChild("Animate")
end

local function getAnimator()
	local character = getCharacter()

	if not character then
		return nil
	end

	local humanoid = character:FindFirstChildOfClass("Humanoid")

	if not humanoid then
		return nil
	end

	return humanoid:FindFirstChildOfClass("Animator")
end

--==================================================
-- SAFE FIND
--==================================================

local function findChild(parent, ...)
	local current = parent

	for _, name in ipairs({...}) do
		if not current then
			return nil
		end

		current = current:FindFirstChild(name)
	end

	return current
end

--==================================================
-- STOP TRACKS
--==================================================

local function stopAnimations()
	local animator = getAnimator()

	if not animator then
		return
	end

	for _, track in ipairs(animator:GetPlayingAnimationTracks()) do
		pcall(function()
			track:Stop(0)
		end)
	end
end

--==================================================
-- ANIMATION OBJECT
--==================================================

local function getAnimationObject(animate, animationName)

	if animationName == "Run" then
		return findChild(animate, "run", "RunAnim")

	elseif animationName == "Walk" then
		return findChild(animate, "walk", "WalkAnim")

	elseif animationName == "Jump" then
		return findChild(animate, "jump", "JumpAnim")

	elseif animationName == "Idle 1" then
		return findChild(animate, "idle", "Animation1")

	elseif animationName == "Idle 2" then
		return findChild(animate, "idle", "Animation2")

	elseif animationName == "Fall" then
		return findChild(animate, "fall", "FallAnim")

	elseif animationName == "Swim" then
		return findChild(animate, "swim", "Swim")

	elseif animationName == "Swim Idle" then
		return findChild(animate, "swimidle", "SwimIdle")

	elseif animationName == "Climb" then
		return findChild(animate, "climb", "ClimbAnim")
	end

	return nil
end

--==================================================
-- SET ANIMATION
--==================================================

local function setAnimation(packName, animationName)

	local animate = getAnimate()

	if not animate then
		return false
	end

	local pack = Packs[packName]

	if not pack then
		return false
	end

	local key = animationName:gsub(" ", "")
	local id = pack[key]

	if not id then
		return false
	end

	local animation =
		getAnimationObject(animate, animationName)

	if not animation then
		warn(
			"VFX Anims: missing animation object:",
			animationName
		)

		return false
	end

	animation.AnimationId =
		"rbxassetid://" .. tostring(id)

	return true
end

--==================================================
-- RESTART ANIMATE
--==================================================

local function restartAnimate()

	local animate = getAnimate()

	if not animate then
		return
	end

	animate.Disabled = true

	task.wait()

	animate.Disabled = false
end

--==================================================
-- APPLY ONE
--==================================================

local function applySingleAnimation()

	stopAnimations()

	if not setAnimation(
		selectedPack,
		selectedAnimation
	) then
		return false
	end

	task.wait()

	restartAnimate()

	currentAppliedPack = selectedPack

	return true
end

--==================================================
-- APPLY FULL PACK
--==================================================

local function applyPack(packName)

	if not Packs[packName] then
		return false
	end

	if not getAnimate() then
		return false
	end

	stopAnimations()

	for _, animationName in ipairs(AnimationNames) do
		setAnimation(
			packName,
			animationName
		)
	end

	restartAnimate()

	currentAppliedPack = packName

	return true
end

--==================================================
-- UI HELPERS
--==================================================

local function corner(object, radius)

	local c = Instance.new("UICorner")

	c.CornerRadius =
		UDim.new(0, radius)

	c.Parent = object

	return c
end

local function stroke(object, color, thickness)

	local s = Instance.new("UIStroke")

	s.Color = color
	s.Thickness = thickness or 1
	s.Transparency = 0

	s.Parent = object

	return s
end

local function label(
	parent,
	text,
	size,
	position,
	fontSize,
	color
)

	local l = Instance.new("TextLabel")

	l.BackgroundTransparency = 1

	l.Size = size
	l.Position = position

	l.Text = text
	l.TextSize = fontSize or 14

	l.Font = Enum.Font.Gotham
	l.TextColor3 = color or WHITE

	l.TextXAlignment =
		Enum.TextXAlignment.Left

	l.Parent = parent

	return l
end

--==================================================
-- COLORS
--==================================================

local BG = Color3.fromRGB(12, 12, 16)
local PANEL = Color3.fromRGB(19, 19, 25)
local PANEL2 = Color3.fromRGB(24, 24, 31)

local BORDER = Color3.fromRGB(45, 45, 56)

local WHITE = Color3.fromRGB(238, 238, 244)
local MUTED = Color3.fromRGB(139, 139, 151)

local PURPLE = Color3.fromRGB(137, 92, 246)
local PURPLE_HOVER = Color3.fromRGB(154, 112, 255)

local GREEN = Color3.fromRGB(91, 205, 126)
local RED = Color3.fromRGB(231, 91, 91)

--==================================================
-- GUI
--==================================================

local gui = Instance.new("ScreenGui")

gui.Name = "VFX Anims"
gui.ResetOnSpawn = false
gui.IgnoreGuiInset = true

gui.Parent =
	player:WaitForChild("PlayerGui")

--==================================================
-- MAIN WINDOW
--==================================================

local frame = Instance.new("Frame")

frame.Name = "VFXAnims"
frame.Size = UDim2.fromOffset(460, 500)

frame.Position =
	UDim2.new(0.5, -230, 0.5, -250)

frame.BackgroundColor3 = BG
frame.BorderSizePixel = 0

frame.Parent = gui

corner(frame, 14)
stroke(frame, BORDER, 1)

--==================================================
-- TOP BAR
--==================================================

local top = Instance.new("Frame")

top.Size =
	UDim2.new(1, 0, 0, 76)

top.BackgroundTransparency = 1

top.Parent = frame

local title = label(
	top,
	"VFX Anims",
	UDim2.fromOffset(300, 28),
	UDim2.fromOffset(24, 15),
	21,
	WHITE
)

title.Font = Enum.Font.GothamBold

local subtitle = label(
	top,
	"Roblox animation packs",
	UDim2.fromOffset(300, 20),
	UDim2.fromOffset(24, 43),
	11,
	MUTED
)

-- status

local status = Instance.new("Frame")

status.Size = UDim2.fromOffset(86, 27)
status.Position =
	UDim2.new(1, -110, 0, 20)

status.BackgroundColor3 =
	Color3.fromRGB(24, 39, 29)

status.BorderSizePixel = 0

status.Parent = top

corner(status, 8)

local statusDot = Instance.new("Frame")

statusDot.Size = UDim2.fromOffset(6, 6)
statusDot.Position = UDim2.fromOffset(10, 10)

statusDot.BackgroundColor3 = GREEN
statusDot.BorderSizePixel = 0

statusDot.Parent = status

corner(statusDot, 10)

local statusText = label(
	status,
	"Ready",
	UDim2.fromOffset(54, 20),
	UDim2.fromOffset(21, 3),
	10,
	GREEN
)

--==================================================
-- CONTENT
--==================================================

local content = Instance.new("Frame")

content.Size =
	UDim2.new(1, -48, 1, -102)

content.Position =
	UDim2.fromOffset(24, 86)

content.BackgroundTransparency = 1

content.Parent = frame

--==================================================
-- PACK LABEL
--==================================================

label(
	content,
	"ANIMATION PACK",
	UDim2.fromOffset(250, 18),
	UDim2.fromOffset(0, 0),
	10,
	MUTED
)

--==================================================
-- PACK SELECTOR
--==================================================

local packButton = Instance.new("TextButton")

packButton.Size =
	UDim2.new(1, 0, 0, 44)

packButton.Position =
	UDim2.fromOffset(0, 23)

packButton.BackgroundColor3 = PANEL
packButton.BorderSizePixel = 0

packButton.Text = selectedPack

packButton.TextColor3 = WHITE
packButton.TextSize = 13
packButton.Font = Enum.Font.GothamMedium

packButton.TextXAlignment =
	Enum.TextXAlignment.Left

packButton.AutoButtonColor = false

packButton.Parent = content

corner(packButton, 8)
stroke(packButton, BORDER, 1)

local packArrow = label(
	packButton,
	"⌄",
	UDim2.fromOffset(28, 28),
	UDim2.new(1, -36, 0, 8),
	16,
	MUTED
)

packArrow.TextXAlignment =
	Enum.TextXAlignment.Center

--==================================================
-- PACK MENU
--==================================================

local packMenu = Instance.new("ScrollingFrame")

packMenu.Size =
	UDim2.new(1, 0, 0, 160)

packMenu.Position =
	UDim2.fromOffset(0, 72)

packMenu.BackgroundColor3 = PANEL2
packMenu.BorderSizePixel = 0

packMenu.ScrollBarThickness = 3
packMenu.ScrollBarImageColor3 = PURPLE

packMenu.CanvasSize =
	UDim2.fromOffset(0, 0)

packMenu.Visible = false
packMenu.ZIndex = 30

packMenu.Parent = content

corner(packMenu, 8)
stroke(packMenu, BORDER, 1)

local packLayout =
	Instance.new("UIListLayout")

packLayout.Padding =
	UDim.new(0, 2)

packLayout.Parent = packMenu

packLayout:GetPropertyChangedSignal(
	"AbsoluteContentSize"
):Connect(function()

	packMenu.CanvasSize =
		UDim2.fromOffset(
			0,
			packLayout.AbsoluteContentSize.Y + 8
		)

end)

--==================================================
-- ANIMATION LABEL
--==================================================

label(
	content,
	"ANIMATION",
	UDim2.fromOffset(250, 18),
	UDim2.fromOffset(0, 88),
	10,
	MUTED
)

--==================================================
-- ANIMATION SELECTOR
--==================================================

local animationButton = Instance.new("TextButton")

animationButton.Size =
	UDim2.new(1, 0, 0, 44)

animationButton.Position =
	UDim2.fromOffset(0, 111)

animationButton.BackgroundColor3 = PANEL
animationButton.BorderSizePixel = 0

animationButton.Text = selectedAnimation

animationButton.TextColor3 = WHITE
animationButton.TextSize = 13
animationButton.Font = Enum.Font.GothamMedium

animationButton.TextXAlignment =
	Enum.TextXAlignment.Left

animationButton.AutoButtonColor = false

animationButton.Parent = content

corner(animationButton, 8)
stroke(animationButton, BORDER, 1)

local animationArrow = label(
	animationButton,
	"⌄",
	UDim2.fromOffset(28, 28),
	UDim2.new(1, -36, 0, 8),
	16,
	MUTED
)

animationArrow.TextXAlignment =
	Enum.TextXAlignment.Center

--==================================================
-- ANIMATION MENU
--==================================================

local animationMenu = Instance.new("Frame")

animationMenu.Size =
	UDim2.new(1, 0, 0, 160)

animationMenu.Position =
	UDim2.fromOffset(0, 160)

animationMenu.BackgroundColor3 = PANEL2
animationMenu.BorderSizePixel = 0

animationMenu.Visible = false
animationMenu.ZIndex = 30

animationMenu.Parent = content

corner(animationMenu, 8)
stroke(animationMenu, BORDER, 1)

local animationLayout =
	Instance.new("UIListLayout")

animationLayout.Padding =
	UDim.new(0, 2)

animationLayout.Parent =
	animationMenu

--==================================================
-- PREVIEW
--==================================================

local preview = Instance.new("Frame")

preview.Size =
	UDim2.new(1, 0, 0, 68)

preview.Position =
	UDim2.fromOffset(0, 169)

preview.BackgroundColor3 = PANEL
preview.BorderSizePixel = 0

preview.Parent = content

corner(preview, 8)
stroke(preview, BORDER, 1)

label(
	preview,
	"CURRENT SELECTION",
	UDim2.fromOffset(200, 15),
	UDim2.fromOffset(14, 9),
	9,
	MUTED
)

local previewValue = label(
	preview,
	selectedPack .. "  •  " .. selectedAnimation,
	UDim2.new(1, -28, 0, 22),
	UDim2.fromOffset(14, 31),
	13,
	WHITE
)

previewValue.Font =
	Enum.Font.GothamMedium

--==================================================
-- BUTTONS
--==================================================

local applyButton = Instance.new("TextButton")

applyButton.Size =
	UDim2.new(0.5, -6, 0, 42)

applyButton.Position =
	UDim2.fromOffset(0, 249)

applyButton.BackgroundColor3 = PURPLE
applyButton.BorderSizePixel = 0

applyButton.Text = "Apply Animation"

applyButton.TextColor3 =
	Color3.new(1, 1, 1)

applyButton.TextSize = 12
applyButton.Font = Enum.Font.GothamBold

applyButton.AutoButtonColor = false

applyButton.Parent = content

corner(applyButton, 8)

local applyPackButton = Instance.new("TextButton")

applyPackButton.Size =
	UDim2.new(0.5, -6, 0, 42)

applyPackButton.Position =
	UDim2.new(0.5, 6, 0, 249)

applyPackButton.BackgroundColor3 = PANEL2
applyPackButton.BorderSizePixel = 0

applyPackButton.Text = "Apply Full Pack"

applyPackButton.TextColor3 = WHITE
applyPackButton.TextSize = 12
applyPackButton.Font = Enum.Font.GothamBold

applyPackButton.AutoButtonColor = false

applyPackButton.Parent = content

corner(applyPackButton, 8)
stroke(applyPackButton, BORDER, 1)

--==================================================
-- FOOTER
--==================================================

local footerLine = Instance.new("Frame")

footerLine.Size =
	UDim2.new(1, 0, 0, 1)

footerLine.Position =
	UDim2.fromOffset(0, 306)

footerLine.BackgroundColor3 = BORDER
footerLine.BorderSizePixel = 0

footerLine.Parent = content

label(
	content,
	"Right Shift",
	UDim2.fromOffset(75, 20),
	UDim2.fromOffset(0, 321),
	10,
	WHITE
)

label(
	content,
	"to open or close VFX Anims",
	UDim2.fromOffset(230, 20),
	UDim2.fromOffset(68, 321),
	10,
	MUTED
)

--==================================================
-- PACK OPTIONS
--==================================================

for index, packName in ipairs(PackNames) do

	local option =
		Instance.new("TextButton")

	option.Size =
		UDim2.new(1, -8, 0, 29)

	option.BackgroundTransparency = 1
	option.BorderSizePixel = 0

	option.Text = packName

	option.TextColor3 = WHITE
	option.TextSize = 12
	option.Font = Enum.Font.Gotham

	option.TextXAlignment =
		Enum.TextXAlignment.Left

	option.AutoButtonColor = false

	option.LayoutOrder = index
	option.ZIndex = 31

	option.Parent = packMenu

	corner(option, 6)

	local padding =
		Instance.new("UIPadding")

	padding.PaddingLeft =
		UDim.new(0, 10)

	padding.Parent = option

	option.MouseEnter:Connect(function()

		option.BackgroundTransparency = 0
		option.BackgroundColor3 =
			Color3.fromRGB(36, 36, 46)

	end)

	option.MouseLeave:Connect(function()

		option.BackgroundTransparency = 1

	end)

	option.Activated:Connect(function()

		selectedPack = packName

		packButton.Text =
			selectedPack

		previewValue.Text =
			selectedPack ..
			"  •  " ..
			selectedAnimation

		packMenu.Visible = false
		dropdownOpen = nil

	end)
end

--==================================================
-- ANIMATION OPTIONS
--==================================================

for index, animationName in ipairs(AnimationNames) do

	local option =
		Instance.new("TextButton")

	option.Size =
		UDim2.new(1, -8, 0, 29)

	option.BackgroundTransparency = 1
	option.BorderSizePixel = 0

	option.Text = animationName

	option.TextColor3 = WHITE
	option.TextSize = 12
	option.Font = Enum.Font.Gotham

	option.TextXAlignment =
		Enum.TextXAlignment.Left

	option.AutoButtonColor = false

	option.LayoutOrder = index
	option.ZIndex = 31

	option.Parent = animationMenu

	corner(option, 6)

	local padding =
		Instance.new("UIPadding")

	padding.PaddingLeft =
		UDim.new(0, 10)

	padding.Parent = option

	option.MouseEnter:Connect(function()

		option.BackgroundTransparency = 0
		option.BackgroundColor3 =
			Color3.fromRGB(36, 36, 46)

	end)

	option.MouseLeave:Connect(function()

		option.BackgroundTransparency = 1

	end)

	option.Activated:Connect(function()

		selectedAnimation = animationName

		animationButton.Text =
			selectedAnimation

		previewValue.Text =
			selectedPack ..
			"  •  " ..
			selectedAnimation

		animationMenu.Visible = false
		dropdownOpen = nil

	end)
end

--==================================================
-- DROPDOWNS
--==================================================

packButton.Activated:Connect(function()

	animationMenu.Visible = false

	if packMenu.Visible then

		packMenu.Visible = false
		dropdownOpen = nil

	else

		packMenu.Visible = true
		dropdownOpen = "pack"

	end

end)

animationButton.Activated:Connect(function()

	packMenu.Visible = false

	if animationMenu.Visible then

		animationMenu.Visible = false
		dropdownOpen = nil

	else

		animationMenu.Visible = true
		dropdownOpen = "animation"

	end

end)

--==================================================
-- HOVER EFFECTS
--==================================================

local function hover(button, normal, over)

	button.MouseEnter:Connect(function()

		TweenService:Create(
			button,
			TweenInfo.new(0.12),
			{
				BackgroundColor3 = over
			}
		):Play()

	end)

	button.MouseLeave:Connect(function()

		TweenService:Create(
			button,
			TweenInfo.new(0.12),
			{
				BackgroundColor3 = normal
			}
		):Play()

	end)
end

hover(
	applyButton,
	PURPLE,
	PURPLE_HOVER
)

hover(
	applyPackButton,
	PANEL2,
	Color3.fromRGB(34, 34, 43)
)

hover(
	packButton,
	PANEL,
	Color3.fromRGB(28, 28, 36)
)

hover(
	animationButton,
	PANEL,
	Color3.fromRGB(28, 28, 36)
)

--==================================================
-- STATUS
--==================================================

local function setStatus(text, color)

	statusText.Text = text
	statusText.TextColor3 = color

end

--==================================================
-- APPLY ANIMATION
--==================================================

applyButton.Activated:Connect(function()

	applyButton.Text = "Applying..."
	setStatus("Working", Color3.fromRGB(245, 190, 80))

	local success =
		applySingleAnimation()

	if success then

		applyButton.Text = "Applied"
		setStatus("Applied", GREEN)

	else

		applyButton.Text = "Failed"
		setStatus("Error", RED)

	end

	task.wait(0.8)

	applyButton.Text =
		"Apply Animation"

	setStatus("Ready", GREEN)

end)

--==================================================
-- APPLY FULL PACK
--==================================================

applyPackButton.Activated:Connect(function()

	applyPackButton.Text =
		"Applying..."

	setStatus(
		"Working",
		Color3.fromRGB(245, 190, 80)
	)

	local success =
		applyPack(selectedPack)

	if success then

		applyPackButton.Text =
			"Applied " .. selectedPack

		setStatus("Applied", GREEN)

	else

		applyPackButton.Text =
			"Failed"

		setStatus("Error", RED)

	end

	task.wait(0.8)

	applyPackButton.Text =
		"Apply Full Pack"

	setStatus("Ready", GREEN)

end)

--==================================================
-- RIGHT SHIFT
--==================================================

UserInputService.InputBegan:Connect(function(
	input,
	gameProcessed
)

	if gameProcessed then
		return
	end

	if input.KeyCode ~= Enum.KeyCode.RightShift then
		return
	end

	menuOpen = not menuOpen

	packMenu.Visible = false
	animationMenu.Visible = false
	dropdownOpen = nil

	if menuOpen then

		frame.Visible = true

		frame.Position =
			UDim2.new(
				0.5,
				-230,
				0.5,
				-235
			)

		TweenService:Create(
			frame,
			TweenInfo.new(
				0.18,
				Enum.EasingStyle.Quint,
				Enum.EasingDirection.Out
			),
			{
				Position =
					UDim2.new(
						0.5,
						-230,
						0.5,
						-250
					)
			}
		):Play()

	else

		local tween =
			TweenService:Create(
				frame,
				TweenInfo.new(
					0.15,
					Enum.EasingStyle.Quint,
					Enum.EasingDirection.In
				),
				{
					Position =
						UDim2.new(
							0.5,
							-230,
							0.5,
							-235
						)
				}
			)

		tween:Play()

		tween.Completed:Connect(function()

			if not menuOpen then
				frame.Visible = false
			end

		end)

	end
end)

--==================================================
-- RESPAWN
--==================================================

player.CharacterAdded:Connect(function(character)

	task.wait(1)

	if currentAppliedPack then
		applyPack(currentAppliedPack)
	end

end)

--==================================================
-- INITIAL
--==================================================

task.spawn(function()

	local character = player.Character

	if character then

		character:WaitForChild("Humanoid")

		task.wait(1)

		applyPack(selectedPack)

	end

end)