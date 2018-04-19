-----------------------------------------------------------------------------------------
-- Created by: Aayman Shameem
-- Created on: Apr 19, 2018
--
-- This code will make the sprite move by touching the arrow buttons on the D-pad
-----------------------------------------------------------------------------------------

-- Character move

local dPad = display.newImage( "./assets/sprites/d-pad.png" )
dPad.x = 150
dPad.y = display.contentHeight - 150
dPad.id = "d-pad"

local upArrow = display.newImage( "./assets/sprites/upArrow.png" )
upArrow.x = 150
upArrow.y = display.contentHeight - 260
upArrow.id = "up arrow"

local downArrow = display.newImage( "./assets/sprites/downArrow.png" )
downArrow.x = 150
downArrow.y = display.contentHeight - 40
downArrow.id = "up arrow"

local leftArrow = display.newImage( "./assets/sprites/leftArrow.png" )
leftArrow.x = 40
leftArrow.y = display.contentHeight - 150
leftArrow.id = "up arrow"

local rightArrow = display.newImage( "./assets/sprites/rightArrow.png" )
rightArrow.x = 260
rightArrow.y = display.contentHeight - 150
rightArrow.id = "up arrow"

local monsterCat = display.newImage( "./assets/sprites/Monstercat.png" )
monsterCat.x = display.contentCenterX
monsterCat.y = display.contentCenterY
monsterCat.id = "the character"
 
function upArrow:touch( event )
    if ( event.phase == "ended" ) then
        -- move the character up
        transition.moveBy( monsterCat, { 
        	x = 0, -- move 0 in the x direction 
        	y = -50, -- move up 50 pixels
        	time = 100 -- move in a 1/10 of a second
        	} )
    end

    return true
end



function downArrow:touch( event )
    if ( event.phase == "ended" ) then
        -- move the character up
        transition.moveBy( monsterCat, { 
        	x = 0, -- move 0 in the x direction 
        	y = 50, -- move down 50 pixels
        	time = 100 -- move in a 1/10 of a second
        	} )
    end

    return true
end



function rightArrow:touch( event )
    if ( event.phase == "ended" ) then
        -- move the character up
        transition.moveBy( monsterCat, { 
        	x = 50, -- move right 50 in the x direction 
        	y = 0, -- move down 0 pixels
        	time = 100 -- move in a 1/10 of a second
        	} )
    end

    return true
end



function leftArrow:touch( event )
    if ( event.phase == "ended" ) then
        -- move the character up
        transition.moveBy( monsterCat, { 
        	x = -50, -- move 0 in the x direction 
        	y = 0, -- move left 50 pixels
        	time = 100 -- move in a 1/10 of a second
        	} )
    end

    return true
end

leftArrow:addEventListener( "touch", leftArrow )
upArrow:addEventListener( "touch", upArrow )
downArrow:addEventListener( "touch", downArrow )
rightArrow:addEventListener( "touch", rightArrow )
