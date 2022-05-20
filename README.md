# twm-pink-theme
how to customize twm.
tldr of https://www.x.org/archive/X11R6.8.1/doc/twm.1.html

How to set Custom shortcuts?
[button | key] = [modifiers] : context : function

button:
"F1";"F2"

modifier:

s=shift

c=control

m=metakey


context:
root Execute the function if the pointer is in the root window.

frame Execute the function if the pointer is in the twm frame.

title Execute the function if the pointer is in the title bar.

window Execute the function if the pointer is in the client window.

icon Execute the function if the pointer is in the associated icon window.

iconmgr Execute the function if the pointer is in the icon manager entry.

all Execute the function no matter where the pointer is


function:

f.autoraise

This function toggles whether or not the selected window is raised whenever entered by the pointer. See the description of the variable AutoRaise.

f.backiconmgr

This function warps the pointer to the previous column in the current icon manager, wrapping back to the previous row if necessary.

f.beep

This function sounds the keyboard bell.

f.bottomzoom

This function is similar to the f.fullzoom function, but resizes the window to fill only the bottom half of the screen.

f.circledown

This function lowers the top-most window that occludes another window.

f.circleup

This function raises the bottom-most window that is occluded by another window.

f.colormap string

This function rotates the colormaps (obtained from the WM_COLORMAP_WINDOWS property on the window) that twm will display when the pointer is in this 

window. The argument string may have one of the following values: "next", "prev", and "default". It should be noted here that in general, the installed 

colormap is determined by keyboard focus. A pointer driven keyboard focus will install a private colormap upon entry of the window owning the colormap. 

Using the click to type model, private colormaps will not be installed until the user presses a mouse button on the target window.

f.deiconify

This function deiconifies the selected window. If the window is not an icon, this function does nothing.

f.delete

This function sends the WM_DELETE_WINDOW message to the selected window if the client application has requested it through the WM_PROTOCOLS window 
property. The application is supposed to respond to the message by removing the indicated window. If the window has not requested WM_DELETE_WINDOW 
messages, the keyboard bell will be rung indicating that the user should choose an alternative method. Note this is very different from f.destroy. The 
intent here is to delete a single window, not necessarily the entire application.

f.deltastop

This function allows a user-defined function to be aborted if the pointer has been moved more than MoveDelta pixels. See the example definition given for Function "move-or-raise" at the beginning of the section.

f.destroy

This function instructs the X server to close the display connection of the client that created the selected window. This should only be used as a last resort for shutting down runaway clients. See also f.delete.

f.downiconmgr

This function warps the pointer to the next row in the current icon manger, wrapping to the beginning of the next column if necessary.

f.exec string

This function passes the argument string to /bin/sh for execution. In multiscreen mode, if string starts a new X client without giving a display argument, the client will appear on the screen from which this function was invoked.

f.focus

This function toggles the keyboard focus of the server to the selected window, changing the focus rule from pointer-driven if necessary. If the selected window already was focused, this function executes an f.unfocus.

f.forcemove

This function is like f.move except that it ignores the DontMoveOff variable.

f.forwiconmgr

This function warps the pointer to the next column in the current icon manager, wrapping to the beginning of the next row if necessary.

f.fullzoom

This function resizes the selected window to the full size of the display or else restores the original size if the window was already zoomed.

f.function string

This function executes the user-defined function whose name is specified by the argument string.

f.hbzoom

This function is a synonym for f.bottomzoom.

f.hideiconmgr

This function unmaps the current icon manager.

f.horizoom

This variable is similar to the f.zoom function except that the selected window is resized to the full width of the display.

f.htzoom

This function is a synonym for f.topzoom.

f.hzoom

This function is a synonym for f.horizoom.

f.iconify

This function iconifies or deiconifies the selected window or icon, respectively.

f.identify

This function displays a summary of the name and geometry of the selected window. If the server supports the SYNC extension, the priority of the client owning the window is also displayed. Clicking the pointer or pressing a key in the window will dismiss it.

f.lefticonmgr

This function similar to f.backiconmgr except that wrapping does not change rows.

f.leftzoom

This variable is similar to the f.bottomzoom function but causes the selected window is only resized to the left half of the display.

f.lower

This function lowers the selected window.

f.menu string

This function invokes the menu specified by the argument string. Cascaded menus may be built by nesting calls to f.menu.

f.move

This function drags an outline of the selected window (or the window itself if the OpaqueMove variable is set) until the invoking pointer button is released. Double clicking within the number of milliseconds given by ConstrainedMoveTime warps the pointer to the center of the window and constrains the move to be either horizontal or vertical depending on which grid line is crossed. To abort a move, press another button before releasing the first button.

f.nexticonmgr

This function warps the pointer to the next icon manager containing any windows on the current or any succeeding screen.

f.nop

This function does nothing and is typically used with the DefaultFunction or WindowFunction variables or to introduce blank lines in menus.

f.previconmgr

This function warps the pointer to the previous icon manager containing any windows on the current or preceding screens.

f.priority string

This function sets the priority of the client owning the selected window to the numeric value of the argument string, which should be a signed integer in double quotes (e.g. "999" ). This function has an effect only if the server supports the SYNC extension.

f.quit

This function causes twm to restore the window's borders and exit. If twm is the first client invoked from xdm, this will result in a server reset.

f.raise

This function raises the selected window.

f.raiselower

This function raises the selected window to the top of the stacking order if it is occluded by any windows, otherwise the window will be lowered.

f.refresh

This function causes all windows to be refreshed.

f.resize

This function displays an outline of the selected window. Crossing a border (or setting AutoRelativeResize) will cause the outline to begin to rubber band until the invoking button is released. To abort a resize, press another button before releasing the first button.

f.restart

This function kills and restarts twm.

f.startwm string

This function kills twm and starts another window manager, as specified by string.

f.righticonmgr

This function is similar to f.nexticonmgr except that wrapping does not change rows.

f.rightzoom

This variable is similar to the f.bottomzoom function except that the selected window is only resized to the right half of the display.

f.saveyourself

This function sends a WM_SAVEYOURSELF message to the selected window if it has requested the message in its WM_PROTOCOLS window property. Clients that accept this message are supposed to checkpoint all state associated with the window and update the WM_COMMAND property as specified in the ICCCM. If the selected window has not selected for this message, the keyboard bell will be rung.

f.showiconmgr

This function maps the current icon manager.

f.sorticonmgr

This function sorts the entries in the current icon manager alphabetically. See the variable SortIconManager.

f.title

This function provides a centered, unselectable item in a menu definition. It should not be used in any other context.

f.topzoom

This variable is similar to the f.bottomzoom function except that the selected window is only resized to the top half of the display.

f.unfocus

This function resets the focus back to pointer-driven. This should be used when a focused window is no longer desired.

f.upiconmgr

This function warps the pointer to the previous row in the current icon manager, wrapping to the last row in the same column if necessary.

f.vlzoom

This function is a synonym for f.leftzoom.

f.vrzoom

This function is a synonym for f.rightzoom.

f.warpring string

This function warps the pointer to the next or previous window (as indicated by the argument string, which may be "next" or "prev") specified in the WindowRing variable.

f.warpto string

This function warps the pointer to the window which has a name or class that matches string. If the window is iconified, it will be deiconified if the variable WarpUnmapped is set or else ignored.

f.warptoiconmgr string

This function warps the pointer to the icon manager entry associated with the window containing the pointer in the icon manager specified by the argument string. If string is empty (i.e. ""), the current icon manager is chosen.

f.warptoscreen string

This function warps the pointer to the screen specified by the argument string. String may be a number (e.g. "0" or "1"), the word "next" (indicating the current screen plus 1, skipping over any unmanaged screens), the word "back" (indicating the current screen minus 1, skipping over any unmanaged screens), or the word "prev" (indicating the last screen visited.

f.winrefresh
This function is similar to the f.refresh function except that only the selected window is refreshed.

f.zoom

This function is similar to the f.fullzoom function, except that the only the height of the selected window is changed.


for example:
"F1"= s : all : f.exec "exec rofi -show run"

colors

you can change colors with names rgb doesn't work or at least I couldn't find a way

