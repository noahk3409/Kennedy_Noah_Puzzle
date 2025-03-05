# HW#2 - Crushing Bugs
**Course:** MMED-1055  
**Author:** Noah Kennedy 
**Date:** 2025/03/05

## About
This project is a drag-and-drop puzzle game. The goal of this project is to fix bugs related to **multiple puzzle pieces in drop zones** and **resetting pieces when changing backgrounds**.

## Bug Fixes 
**Bug #1:** 
- Problem: Users could drop more than one puzzle piece into a single drop zone.
- Solution: 
    function handleDrop(e) {
    e.preventDefault();
    console.log('dropped something on me');

    // Allow only one piece in the drop zone
    if (this.children.length === 0) {
        this.appendChild(draggedPiece);
    } else {
        console.log('Drop zone already occupied!');
    }

**Bug#2:**
- Problem: When switching backgrounds, pieces remained in the drop zones instead of resetting to the left panel.
- Solution: 
    
    function changeBGImage() {
    // Reset all puzzle pieces before changing the background
    puzzlePieces.forEach(piece => document.querySelector('.puzzle-pieces').appendChild(piece));

    // Change the background image
    puzzleBoard.style.backgroundImage = `url(images/backGround${this.id}.jpg)`;

## How to Use
1. Clone this repository
2. Open "index.html" in a browser
3. Drag and drop puzzle pieces into drop zones.
