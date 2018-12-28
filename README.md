# Understand viewport

This element (<meta name="viewport" content="width=device-width">)
is often used in our html file.But what does this do? 

## An historical situation

- Before modern cell phone was popular, screens' width of most devices is larger than 960px. And developers thought their webpages are larger than 960px and then deal with it.

- With the modern cell phone's popularisation, screens' width of cellphone is too narrow to suit PC-side-optimized webpage design.
- How does a 320px width cellphone to render those big webpages?
- There is a solution, such as
  - iPhone5's screen-width is 320px, but it pretend it 
    has a 980px width viewport. 
  - iPhone renders the webpage to this viewport.
  - but iPhone's screen is too small to represent this viewport
  - iPhone will zoom in the viewport to suit the screen 
  - so, Render is successful. But it is 320/980 times smaller than its view on PC

this is an [example](https://bitfish-xyz.github.io/viewport/no-viewport.html). You can feel the difference if you load it in both cellphone and PC. As you can see, any normal size will be zoom in cellphone.

Whit the time passing, more and more developers are trying to design a responsive webpage. And they optimized their pages for cellphones.

And this historical solution is out of time: it shouldn't zoom in the webpage when developer had designed a cellphone-optimized webpage.

Today, if you add the element to your html file, browser will set viewport's width to device's width.

- If <meta name="viewport" content="width=device-width"> is omitted:
  - no effect to browser on PC
  - browser on cellphone's viewport width may be 980px or 760px(dependant on browser) and webpage will be zoom in
- else
  - browser on cellphone's viewport width will be screen.width, no zoom in

such as this [example](https://bitfish-xyz.github.io/viewport/viewport.html)

- get device-width width `screen.width`
- get browser's outer width with `window.outerWidth`
- get browser's inner width with `window.innerWidth`
- get browser's viewport's width with `document.documentElement.clientWidth`