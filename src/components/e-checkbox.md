#### `single checkbox`

Always use **v-model** to bind value to form elements!
```vue
<template>
<div>
  <div style="display: block;">
    <e-checkbox v-model="checked" :name="name" :value="value" :display-name="value">example</e-checkbox>
  </div>
  
  <div class="spacing--top-15">
    <pre>checked: {{ checked }}</pre>
  </div>

</div>
</template>

<script>
  export default {
    name: 'example',
    data: () => ({
      name: 'xyz',
      checked: false,
      value: 'single Checkbox'
    })
  };
</script>
```


#### `multiple checkboxes`
Use Array instead of Boolean for multiple checkboxes, which share the same v-model. 

```vue
<template>
<div>

    <e-checkbox 
    v-for="item in items"
    :key="item.id" 
    v-model="checked" 
    :name="item.name" 
    :value="item.value" 
    :display-name="item.displayName"
    style="margin-bottom: 10px">example</e-checkbox>
  
  <div class="spacing--top-15">
    <pre>checked: {{ checked }}</pre>
    <pre>items: {{ items }}</pre>
  </div>

</div>
</template>

<script>
  export default {
    name: 'example',
    data: () => ({
      // The list of items we need to do operation on
      items: [
        {id: 1, name:'multiple', value: 'checkbox1', displayName: 'Checkbox 1'},
        {id: 2, name:'multiple', value: 'checkbox2', displayName: 'Checkbox 2'},
        {id: 3, name:'multiple', value: 'checkbox3', displayName: 'Checkbox 3'}
      ],
      
      // The list of IDs of checked items
      checked: ['checkbox2']
    })
  };
</script>
```

#### `checked`
```vue
<template>
<div>

  <e-checkbox checked v-model="checked" :name="name" :value="value" :display-name="value">example</e-checkbox>
  
</div>
</template>

<script>
  export default {
    name: 'example',
    data: () => ({
      name: 'checked',
      checked: true,
      value: 'checked'
    })
  };
</script>
```

#### `disabled`
```vue
<template>
<div>

  <e-checkbox disabled v-model="checked" :name="name" :value="value" :display-name="value">example</e-checkbox>
  
</div>
</template>

<script>
  export default {
    name: 'example',
    data: () => ({
      name: 'disabled',
      checked: true,
      value: 'disabled'
    })
  };
</script>
```


