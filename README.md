# BootPopup

Popup dialog boxes for Bootstrap.

## Demos

See the demos in the Homepage: http://www.bootpopup.tk/#examples


## API

### `bootpopup.alert(message[, title[, callback]])`
  
Shows an alert dialog box.

- **message**:
  - `(string)` message of the alert
- **title**:
  - `(string)` title of the alert. Default value is page title
  - `(function)()` callback when the alert is dismissed
- **callback**:
  - `(function)()` callback when the alert is dismissed


### `bootpopup.confirm(message[, title[, callback]])`

Shows a confirm dialog box.

- **message**:
  - `(string)` message to confirm
- **title**:
  - `(string)` title of the confirm dialog. Default value is page title
  - `(function)(answer)` callback when the confirm is answered. `answer` will be `true` if the anwser was yes and `false` if it was no. If dismissed, the default answer is no
- **callback**:
  - `(function)(answer)` callback when the confirm is answered. `answer` will be `true` if the anwser was yes and `false` if it was no. If dismissed, the default answer is no


### `bootpopup.prompt(label[, type[, message[, title[, callback]]]])`

Shows a prompt dialog box, asking to input a value.

- **label**:
  - `(string)` label of the value being asked
- **type**:
  - `(string)` type of the value being asked. This corresponds to the [HTML input types](http://www.w3schools.com/tags/att_input_type.asp). Default value is `text`
  - `(function)(answer)`
- **message**:
  - `(string)` message shown before the asked value. Default value is *Provide a `type` for:*
  - `(function)(answer)`
- **title**:
  - `(string)` title of the prompt dialog. Default value is page title
  - `(function)(answer)`
- **callback**:
  - `(function)(answer)`


## Examples

Open `index.html` to see the library in action.

- Alert:

        bootpopup.alert("Hi there");

- Confirm:
        
        bootpopup.confirm("Do you confirm this message?");

- Prompt:
		
        bootpopup.prompt("Name");

- Customized prompt:

        bootpopup({
            title: "Add image",
            content: [
                { p: {text: "Insert image info here:"}},
                { input: {type: "text", label: "Title", name: "title", placeholder: "Description for image"}},
                { input: {type: "text", label: "Link", name: "link", placeholder: "Hyperlink for image"}}],
            cancel: function(data) { alert("Cancel"); },
            ok: function(data,e) { console.log(data,e); },
            complete: function() { alert("complete"); },
        });
