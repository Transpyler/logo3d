# logo3d

A logo-like library that uses `Voxel.js <http://voxeljs.com>` to draw in a 3d canvas of voxels 
(3d pixels). Logo3d a Javascript and a Python interfaces (via a webbrowser using 
`eel <https://pypi.org/project/Eel/>`). It is inspired in the turtle graphics mode
of Simon Papert's LOGO language, but with a 3d twist.

## How does it work?

You control a turtle in 3d space by using simple functions to move it around. As the turtle moves, 
it may draw or remove voxels from the screen. Since 3d navigation is much harder than 2d, we 
constraint all movements to a discrete cube of pixels with only right angle rotations.

This code draws a cube:

.. code-block:: javascript

    # Draw a square of size 4 voxels
    for (let i=0; i < 4; i++) {
        forward(4); // move 4 voxels forward
        turn(1);    // make 1 turn of 90 degrees to the right
    }
    
   
Other important functions
    
.. code-block:: javascript
    
    // Movement
    forward/backward(n) -- advance by the given number of voxels
    sideways(n)         -- move sideways: n > 0 goes to the right and n < 0 to the left
    up/down(n)          -- move in the vertical direction relative to the current orientation
    goto(i, j, k)       -- change position instantly without drawing
    
    // Rotation
    roll(n)  -- rotate clockwise n steps of 90 degrees around the main axis (counterclockwise: n < 0)
    turn(n)  -- rotations around the vertical axis.
    pitch(n) -- rotations around the lateral axis.
    
    // Painter
    material(name) -- choose the drawing material (grass, rock, solid, none, erase, etc)
    ?color(color)   -- tint material material with the given color
    
    
    // Inspection
    pos()   -- get current position
    angle() -- ???
    quaternion?
    matrix --?
    
    // Global
    clear()  -- clear screen
    reset()  -- clear screen and put turtle back to initial position
    
    // Lib of objects
    stamp(name) -- draw some object in current position (tree, human, ...)
    ?text(text) -- draw some text on screen
    draw()      -- apply material in the current position
    
    // probably more...
