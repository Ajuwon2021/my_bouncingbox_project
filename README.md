# Welcome to My Bouncing Box
***

## Task
To create a bouncing box with JavaScript codes.

## Description
An html file and javascript code to produce a bouncing box. The box moves diagonally.

## Installation
There is nothing to install here than to use a static page.

## Usage


    const box=document.getElementById('my_bouncing_box')
    const main = document.getElementById('main')

    
let leftright = Math.floor(Math.random() * 2)
let right = leftright? true:false
let updown = Math.floor(Math.random() * 2)
let up =updown? true:false
let velocity = 3

let boxmove = setInterval(() => {
    let boxbounds = box.getBoundingClientRect()
    let boardbounds = main.getBoundingClientRect()
    let boxboundsleft = parseInt(boxbounds.left)
    let boxboundsright = parseInt(boxbounds.right)
    let boxboundstop = parseInt(boxbounds.top)
    let boxboundsbottom = parseInt(boxbounds.bottom)
    let boxtop=Math.floor(parseInt(window.getComputedStyle(box).getPropertyValue("top")))
    let boxleft=Math.floor(parseInt(window.getComputedStyle(box).getPropertyValue("left")))

if (right && up) {
    box.style.top = boxtop - velocity + "px"
    box.style.left = boxleft + velocity + "px"
}

if (!right && up) {
    box.style.top = boxtop - velocity + "px"
    box.style.left = boxleft - velocity + "px"
}

if (right && !up) {
    box.style.top = boxtop + velocity + "px"
    box.style.left = boxleft + velocity + "px"
}

if (!right && !up) {
    box.style.top = boxtop + velocity + "px"
    box.style.left = boxleft - velocity + "px"
}

if (boxboundstop <= boardbounds.top) {
    leftright = Math.floor(Math.random()*2)
    right = leftright?true:false
    up = false
}

if (boxboundsbottom >= boardbounds.bottom) {
    leftright = Math.floor(Math.random()*2)
    right = leftright?true:false
    up = true
}

if (boxboundsright >= boardbounds.right) {
    right = false
    updown = Math.floor(Math.random()*2)
    up = updown?true:false
}

if (boxboundsleft <= boardbounds.left) {
    right = true
    updown = Math.floor(Math.random()*2)
    up = updown?true:false
}


}, 1)

### The Core Team

<span><i>Made at <a href='https://qwasar.io'>Qwasar SV -- Software Engineering School</a></i></span>
<span><img alt='Qwasar SV -- Software Engineering School's Logo' src='https://storage.googleapis.com/qwasar-public/qwasar-logo_50x50.png' width='20px'></span>
