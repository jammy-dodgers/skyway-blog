WIP

# Enemy designs

In testing, I had one default enemy design: The sawblade. It moves back and forth on a line, and it'll hurt if you touch it. Pretty simple, but you can't just make an entire game out of sawblades. This isn't Ravenholm.

This part really bogged down my workflow for a while. Implementation is easy, but trying to think of enemy designs is an issue.

I opted at this point to focus on deciding *behaviour*, and then think of actual imagery later. 'Bottom-up design', as is used in '*Magic: The Gathering*' - we design the mechanics first, and then later work out the theming of it.

So, first of all, lets make up some placeholder images for our enemies.


```lua
function EnemyPlaceholderImage(name, w, h)
    local img = gfx.image.new(w, h)
    gfx.pushContext(img)
    gfx.setColor(gfx.kColorWhite)
    gfx.fillRect(0,0,w,h)
    gfx.setColor(gfx.kColorBlack)
    gfx.drawRect(0,0,w,h)
    Noble.Text.draw(name, 1, 1)
    gfx.popContext()
    return img
end
```

Once again, we'll just be doing this in-code for simplicity. The placeholder we get is a box with the name painted on.