# 4d-tips-named-selection-listbox
Example of using named-selection listbox (v14).

Featured
---
* Zoom: enlarge font size with ```On Resize``` event.

* Sort: perform sorting with ```On Header Click``` event.

* Sort: support record update with ```On Drop``` event.

* Entry: filter locked record with ```On Before Data Entry``` event.

* Entry: unload current record aftet ```CUT NAMED SELECTION```.

* Other: pseudo-dynamic (```"$"+Generate UUID```) named selection and highlight set names.

Discussion
---

**Dynamic named selection and highlight set**

If you specify the selection/set name in the property list, there is nothing to prevent you from using it in another form, or another instance of the same form. When that is the case, you can't really clear the selection/set, or the other form will turn blank. Thanks to ```LISTBOX SET TABLE SOURCE``` and ```LISTBOX GET TABLE SOURCE``` it is possbile to bind a different selection/set for each instance.

**Resize management**

The form has a resizable rectangle object which is size 0 and transparent. By measuring its size during ```On Resize``` it is possible to determine how much the form has grown/shrunk from its previous size. Notice the object is visible (not hidden) according to its  property. Making it invisible breaks this technique.

**Sorting**

Sorting by header click is not supported in named-selection based boxes, but the example illustrates how it can be done by managing the ```On Header Click``` event.

**Drag and Drop***

```On Row Moved``` is not supported in named-selection based boxes, but the example illustrates how it can be done by some coding with ```Drop position``` and ```DRAG AND DROP PROPERTIES```. ```On Begin Drag Over``` is not very useful, as there are no straightforward ways to know on which row the event has fired.

![](https://github.com/miyako/4d-tips-named-selection-listbox/blob/master/images/screenshot.png)
