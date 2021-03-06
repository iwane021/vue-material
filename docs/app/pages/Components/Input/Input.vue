<example src="./examples/TextFields.vue" />
<example src="./examples/ErrorsMessages.vue" />
<example src="./examples/Counters.vue" />
<example src="./examples/FieldIcons.vue" />
<example src="./examples/InlineActions.vue" />

<template>
  <page-container centered :title="$t('pages.input.title')">
    <div class="page-container-section">
      <p>Text fields allows users to input, edit, and select text, typically inside forms but they can appear in other places, like dialog boxes and search.</p>
      <p>Vue Material fields works with a <code>md-field</code> as a wrapper with a input component inside, that can be <code>md-input</code>, <code>md-textarea</code> or even a <code>md-select</code>.</p>
      <note-block tip>Selects have its own <router-link to="/components/select">documentation page</router-link>, dedicated to show better examples on how to use it.</note-block>
    </div>

    <div class="page-container-section">
      <h2>Text Fields</h2>

      <p>Fields mimics the HTML5 attributes to keep the same compatibility with native inputs, but giving extra options. This allows Vue Material to setup the <code>md-field</code> according with the input options.</p>
      <p>You will be able to set the same properties of a regular <code>input</code> element on <code>md-input</code>. This is also valid for <code>textarea</code> and <code>select</code>. Take a look:</p>
      <code-example title="Input and Textarea" :component="examples['text-fields']" />
    </div>

    <div class="page-container-section">
      <h2>Errors and Messages</h2>

      <p>Vue Material have validation states to show error messages. You can use it along with other Vue 3rd party validation libraries, like Vuelidate or Vee-Validate:</p>
      <code-example title="Validation" :component="examples['errors-messages']" />
    </div>

    <div class="page-container-section">
      <h2>Character count</h2>

      <p>You can use character counters where you need to limit the user input, like on Twitter's 280 character tweet:</p>
      <code-example title="Counter" :component="examples['counters']" />
    </div>

    <div class="page-container-section">
      <h2>Icons</h2>

      <p>Sometimes we may want to differentiate our inputs based on it content value:</p>
      <code-example title="Outside and inline icons" :component="examples['field-icons']" />
    </div>

    <div class="page-container-section">
      <h2>Inline Actions</h2>

      <p>Fields can have a clearable feature to make easy for users to clear the value. And to be easier to type passwords we can show a toggle button to reveal the password. This is really useful for mobile applications:</p>
      <code-example title="Clear and password" :component="examples['inline-actions']" />

      <api-item title="API - md-field">
        <p>The following options can be applied to any field:</p>

        <api-table :headings="field.headings" :props="field.props" slot="props" />
      </api-item>

      <api-item title="API - md-input">
        <p>The following options can be applied to any input:</p>

        <api-table :headings="input.headings" :props="input.props" slot="props" />
      </api-item>

      <api-item title="API - md-textarea">
        <p>The following options can be applied to any textarea:</p>

        <api-table :headings="textarea.headings" :props="textarea.props" slot="props" />
      </api-item>

      <note-block tip>Any <code>input</code> or <code>textarea</code> attributes can be used on <code>md-input</code>/<code>md-textarea</code> respectively.</note-block>
    </div>
  </page-container>
</template>

<script>
  import examples from 'docs-mixins/docsExample'

  export default {
    name: 'DocInput',
    mixins: [examples],
    data: () => ({
      field: {
        headings: ['Name', 'Description', 'Default'],
        props: [
          {
            name: 'md-inline',
            type: 'Boolean',
            description: 'Make the label inline. This means that the label will disappear when the input receives a focus.',
            defaults: 'false'
          },
          {
            name: 'md-counter',
            type: 'Boolean',
            description: 'Enable the character counter. Only works with fields that have a <code>md-input</code> or <code>md-textarea</code> with a <code>maxlength</code> or <code>md-counter</code> attributes.',
            defaults: 'false'
          },
          {
            name: 'md-clearable',
            type: 'Boolean',
            description: 'Add a clear button on the right of the input.',
            defaults: 'false'
          },
          {
            name: 'md-toggle-password',
            type: 'Boolean',
            description: 'Add a toggle button on the right of the input to reveal/hide the password. Only works with fields that have a <code>md-input</code> with type password.',
            defaults: 'false'
          }
        ]
      },
      input: {
        headings: ['Name', 'Description', 'Default'],
        props: [
          {
            name: 'v-model',
            type: 'String|Number|Boolean|Array',
            description: 'The model variable to bind the input value',
            defaults: 'null'
          },
          {
            name: 'type',
            type: 'String',
            description: 'The input type. Similar to HTML5 type attribute.',
            defaults: 'text'
          },
          {
            name: 'placeholder',
            type: 'String',
            description: 'The input placeholder. Similar to HTML5 placeholder attribute.',
            defaults: 'null'
          },
          {
            name: 'required',
            type: 'Boolean',
            description: 'The input required. Similar to HTML5 required attribute.',
            defaults: 'false'
          },
          {
            name: 'id',
            type: 'String',
            description: 'The input id. Similar to HTML5 id attribute.',
            defaults: 'a random string'
          },
          {
            name: 'name',
            type: 'String',
            description: 'The input name. Similar to HTML5 name attribute.',
            defaults: 'null'
          },
          {
            name: 'disabled',
            type: 'Boolean',
            description: 'Disable the input and prevent it interactions.',
            defaults: 'false'
          },
          {
            name: 'maxlength',
            type: 'Number',
            description: 'Enable the counter for the field and set a maxlength',
            defaults: 'null'
          },
          {
            name: 'md-counter',
            type: 'Number',
            description: 'Enable the counter for the field. This is useful when you want only a counter without set a maxlength',
            defaults: 'null'
          }
        ]
      },
      textarea: {
        headings: ['Name', 'Description', 'Default'],
        props: [
          {
            name: 'v-model',
            type: 'String|Number|Boolean|Array',
            description: 'The model variable to bind the textarea value',
            defaults: 'null'
          },
          {
            name: 'placeholder',
            type: 'String',
            description: 'The textarea placeholder. Similar to HTML5 placeholder attribute.',
            defaults: 'null'
          },
          {
            name: 'required',
            type: 'Boolean',
            description: 'The input required. Similar to HTML5 required attribute.',
            defaults: 'false'
          },
          {
            name: 'id',
            type: 'String',
            description: 'The textarea id. Similar to HTML5 id attribute.',
            defaults: 'a random string'
          },
          {
            name: 'name',
            type: 'String',
            description: 'The textarea name. Similar to HTML5 name attribute.',
            defaults: 'null'
          },
          {
            name: 'disabled',
            type: 'Boolean',
            description: 'Disable the textarea and prevent it interactions.',
            defaults: 'false'
          },
          {
            name: 'maxlength',
            type: 'Number',
            description: 'Enable the counter for the field and set a maxlength',
            defaults: 'null'
          },
          {
            name: 'md-counter',
            type: 'Number',
            description: 'Enable the counter for the field. This is useful when you want only a counter without set a maxlength',
            defaults: 'null'
          },
          {
            name: 'md-autogrow',
            type: 'Boolean',
            description: 'Enable the textarea autogrow',
            defaults: 'false'
          }
        ]
      }
    })
  }
</script>
