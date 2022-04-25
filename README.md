# Examples
  https://codepen.io/CyBeRrRrr/pen/NWXVZow?editors=0110

# Start
  To start, just copy the `chooser.js` and `chooser.css` files.
  Then connect them to the head of your html file

  <script defer="defer" src="chooser.js"></script>
  <link href="chooser.css" rel="stylesheet">

  Then connect your file with scripts, such as `scripts.js`
  <script defer="defer" src="scripts.js"></script>

  and create a new Chooser instance in your file using the object with the settings.

# Example of a settings object
```js
  const options = {
    el: 'select',
    placeholder: 'some_placeholder',
    // current: 2,
    data: [
      {
        value: 'some_value',
        attr: {
          'some_attr': 'some_value'
        }
      },
      { value: 'some_value' },
      { value: 'some_value' },
    ],
    classList: {
      label: 'some-class__label',
      wrapper: 'some-class__wrapper',
      current: 'some-class__button',
      list: 'some-class__list',
      item: 'some-class__item',
    }
  }

  const select = new Chooser(options);
```

# Complete list of settings
```js
  const select = new Chooser({
  el: 'filter',
//    -- 'el': Root element Id
  placeholder: 'some_placeholder',
//    -- 'placeholder': default "choser"
  current: 2,
  group: 'some_group',
//    -- add group to hide the names of one group
  label: 'some_label',
//    -- 'label': default "Выберите элемент:". required element. is an ARIA lable
  data: [
    {
      value: 'some_value',
      attr: {
        'some_attr': 'some_value',
        'some_attr': 'some_value',
        'some_attr': 'some_value',
//        -- 'attr': any attributes can be added (key - value)
      },
      id: 'some_unique_id',
//        -- 'id': item id is assigned automatically by the index of the item in the array.
//            If necessary, you can reassign it.
//            Used to select an element and focus on an element:
//            (select.select (chooserId), select.focuse (chooserId)).
      group: 'some_name',
//        -- add group to hide the names of one group
   },

    {
      value: 'some_value',
      attr: {
        'some_attr': 'some_value',
        'some_attr': 'some_value',
        'some_attr': 'some_value',
      },
      id: 'some_unique_id'
    },

    { value: 'some_value' },
  ],
  classList: {
    label: 'some-class__label',
    wrapper: 'some-class__wrapper',
    current: 'some-class__button',
    list: 'some-class__list',
    item: 'some-class__item',
  }
});
```
#  Aattributes
```js
  `data-chooser_no_close=${id}` // do not close this.checkMiss(event);
```
#  Classes
  focused - stylizing the state of focus when accessing from the keyboard
  selected - stylizing the state of selected item
  disabled - stylizing the state of disabled item
            (is automatically added to all items in the group except the selected)
            it with this class becomes selectable and skipped when selected from the keyboard