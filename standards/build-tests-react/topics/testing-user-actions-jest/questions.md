* Why should you use the `user-event` library instead of using Testing Library's built-in `fireEvent`?
* How do you press a modifier key in a `user-event` string?
* How do you add delays between keystrokes to simulate typing in `user-event`?
* If you add delays to an action in `user-event`, what do you always have to do?
* How do you release a modifier key in a `user-event` string?
* How would you write a `user-event` string that types the word "me test", and then:
  * Uses the home key to go the beginning of the line
  * Uses the shift and arrow keys to highlight the word "me"
  * Uses control and `x` to cut it
  * Deletes the extra space
  * Use the end key to go the end of the line
  * Add a space to it
  * Uses control and `v` to paste "me"
