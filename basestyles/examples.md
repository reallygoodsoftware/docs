---
custom-class: ui-styled-text
---

# Examples

> The purpose of this page is to showcase some of the elements at-a-glance. If you want to see the code for an element, either view the source on this page, or go to the specific page of the element you're interested in.


<!-- region examples -->

## .ui-button

<div class="ui-ox my-6">
  <div class="flex gap-x-2">
    <button class="ui-button">
      Simple Button
    </button>
    <button class="ui-button --solid">
      Solid Button
    </button>
    <button class="ui-button --minimal">
      Minimal Button
    </button>
    <span class="ui-link ml-2">
      Just a link
    </span>
  </div>
</div>
<div class="ui-bx my-6">
  <div class="flex gap-x-2">
    <button class="ui-button --motion-forward">
      With some motion
      <img class="no-zoom" src="/icons/heroicons/arrow-right.svg" />
    </button>
    <button class="ui-button --rounded">
      <img src="/icons/heroicons/envelope-outline.svg" />
      rounded
    </button>
    <button class="ui-button --minimal">
      <img src="/icons/heroicons/envelope-outline.svg" />
    </button>
    <button class="ui-button --rounded --minimal">
      <img src="/icons/heroicons/ellipsis-horizontal.svg" />
    </button>
  </div>
</div>


## .ui-toggle

<div class="ui-box my-6 ui-styled-text-unset">
  <div class="flex w-full justify-between">
    <div>
      <div class="ui-titlepair">
        <h3 class="--title">Toggle</h3>
        <p class="--description">Use the .ui-toggle class. See markup for details. </p>
      </div>
    </div>
    <div class="flex items-center">
      <!-- Rounded switch -->
      <label class="ui-toggle">
        <input type="checkbox">
        <span class="--slider"></span>
      </label>
    </div>
  </div>
</div>

## .ui-form

<form id="form1" class="ui-box my-6 ui-form" action="/docs">
  <div class="ui-tuple flex flex-col gap-y-1">  
    <div class="grid grid-cols-2 gap-x-4">
      <div>
        <label for="first_name">First Name</label>
        <input id="first_name" type="text" placeholder="First Name" />
      </div>
      <div>
        <label for="last_name">Last Name</label>
        <input id="last_name" type="text" placeholder="Last Name" />
      </div>
    </div>
    <div>
      <label for="options">Select</label>
      <select id="options">
        <option value="1">Option 1</option>
        <option value="2">Option 2</option>
        <option value="3">Option 3</option>
      </select>
    </div>
    <div>
      <label for="options">Dropdown</label>
      <div v-pre :scope="
          inputId=new Date().getTime(),
          options=[{name:'Pear',id:'pear'},{name:'Option 2',id:'option2'},{name:'Option 3',id:'option3'}],
          filteredOptions=[],
          selectedOption=null,
          highlightedOption=null,
          open=false
        ">
        <div class="ui-select" :class="scope.open ? '--open' : ''" >
          <button :text="scope.selectedOption ? scope.selectedOption.name : 'Select An Option'" type="button" class="--trigger" 
            :click="scope.open = !scope.open; document.getElementById(scope.inputId).focus();">
            Select An Option
          </button>
          <div class="--drawer">
            <input class="--searchbox" type="text" placeholder="Search..."
              :id="scope.inputId" 
              :change="
                scope.filteredOptions = scope.options.filter(option =>
                  option.name.toLowerCase().includes($event.target.value.toLowerCase()) ||
                  option.id.toLowerCase().includes($event.target.value.toLowerCase())
                );
                scope.highlightedOption = scope.filteredOptions[0];
              "
              />
            <div class="--options" :each="option in scope.filteredOptions" >
              <button type="button" 
                :press="scope.selectedOption = option; scope.open = false;" 
                :text="option.name"></button>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div>
      <label for="options">Input Group</label>
      <div class="ui-input-group">
        <input id="first_name" type="text" placeholder="First Name" />
        <input id="middle_name" type="text" placeholder="Middle Name" />
        <input id="last_name" type="text" placeholder="Last Name" />
      </div>
    </div>
  </div>
  <div class="--bottom">
    <div>
      <a class="ui-button --minimal --motion-backward">
        <img src="/icons/heroicons/arrow-left.svg" />
        Back
      </a>
    </div>
    <div class="flex gap-x-2">
      <a class="ui-button --motion-forward" >
        Save Draft
        <img src="/icons/heroicons/paper-airplane-outline.svg" />
      </a>
      <button type="submit" class="ui-button --solid --motion-forward" form="form1">
        Go
      </button>
    </div>
  </div>
</form>

## .ui-floating-input

<div class="ui-box my-6">
  <form class="ui-form">
    <div class="grid grid-cols-2 gap-x-3">
      <div>
        <div class="ui-floating-input">
          <input type="text" placeholder=" " name="first_name" id="first_name" />
          <label>First Name</label>
        </div>
      </div>
      <div>
        <div class="ui-floating-input">
          <input type="text" placeholder=" " name="first_name" id="first_name" />
          <label>Last Name</label>
        </div>
      </div>
    </div>
  </form>
</div>

## .ui-tabnav

<div class="ui-box ui-styled-text-unset my-6">
  <div class="--top">
    <div class="ui-titlepair">
      <h2 class="--title">Tabnavs</h2>
      <span class="--description">
        Groups of links spread out horizontally
      </span>
    </div>
  </div>
  <div class="ui-titlepair mb-5 --sm">
    <h2 class="--title">Ares</h2>
  </div>
  <div v-pre class="ui-tabnav --ares mb-10" :scope="activeTab='content'">
    <div :class="scope.activeTab =='content' ? 'active' : ''" class="active">
      <button :click="scope.activeTab='content'" >
        Content
      </button>
    </div>
    <div :class="scope.activeTab =='setup' ? 'active' : ''">
      <button :click="scope.activeTab='setup'">
        Setup
      </button>
    </div>
  </div>
  <div class="ui-titlepair --sm mb-10">
    <h2 class="--title">Hades</h2>
  </div>
  <div v-pre class="ui-tabnav --hades" :scope="activeTab='content'">
    <a :class="scope.activeTab =='content' ? 'active' : ''" :click="scope.activeTab='content'">
      <div class="ui-titlepair --sm" href="#">
        <div class="--title">Content</div>
        <span class="--description">The main content</span>
      </div>
    </a>
    <a :class="scope.activeTab =='setup' ? 'active' : ''" :click="scope.activeTab='setup'" >
      <div class="ui-titlepair --sm" href="#">
        <div class="--title">Setup</div>
        <span class="--description">Configure Your Integration</span>
      </div>
    </a>
  </div>
</div>

## .ui-search-input

<div class="ui-box flex flex-col gap-y-4 my-6">
  <div class="ui-titlepair">
    <div class="--title">
      Search Input
    </div>
    <div class="--description">
      Use within a form or as standalone
    </div>
  </div>
  <input type="search" placeholder="Search..." class="ui-search-input" />
</div>

## .ui-tuple

<div class="ui-box my-6">
  <div class="--top">
    <div class="ui-titlepair">
      <h2 class="--title">Tuples</h2>
      <span class="--description">
        A tuple is a div with a separator, content on the left, and content on the right.
      </span>
    </div>
  </div>
  <div class="ui-tuple pb-6">
    <div class="--item">
      <div class="--left">
        <div class="ui-titlepair --sm">
          <h3 class="--title">Business Starter Plan</h3>
          <p class="--description">Get custom email (@yourcompany.com), 100 participant video meetings, and more.</p>
        </div>
      </div>
      <div class="--right">
        <a href="#" class="ui-link --motion-forward">
          Upgrade
          <img src="/icons/heroicons/arrow-right.svg" />
        </a>
      </div>
    </div>
    <div class="--item">
      <div class="--left">
        <div class="ui-titlepair --sm">
          <h3 class="--title">Business Starter Plan</h3>
          <p class="--description">Get custom email (@yourcompany.com), 100 participant video meetings, and more.</p>
        </div>
      </div>
      <div class="--right">
        <a href="#" class="ui-link">Upgrade</a>
      </div>
    </div>
  </div>
</div>

## .ui-tooltip

<div class="ui-box my-6">
  <div class="--top">
    <div class="ui-titlepair">
      <h2 class="--title">Tooltips</h2>
      <span class="--description">
        Tooltips are based on hint.css. Currently they don't support html content.
      </span>
    </div>
  </div>
  <button class="ui-button --solid --motion-forward ui-tooltip--top mr-4" aria-label="Use the ui-tooltip--top class">
    Tooltip Top
  </button>

  <button class="ui-button --solid --motion-forward ui-tooltip--right" aria-label="Use the ui-tooltip--right class">
    Tooltip Right
  </button>
</div>

### .ui-box

<div class="ui-box my-6">
  <div class="ui-titlepair">
    <div class="--title">
      Title
    </div>
    <div class="--description">
      Description
    </div>
  </div>
  <div class="--bottom">
    Put the content of your bottom section here
  </div>
</div>


## .ui-titlepair

<div class="ui-bx my-6">
  <div class="flex flex-col gap-y-5">
    <div class="ui-titlepair --lg">
      <div class="--title">
        This is a large title pair
      </div>
      <div class="--description">
        With Description
      </div>
    </div>
    <div class="ui-titlepair">
      <div class="--title">
        This is a normal title pair
      </div>
      <div class="--description">
        With Description
      </div>
    </div>
    <div class="ui-titlepair --sm">
      <div class="--title">
        This is a small title pair
      </div>
      <div class="--description">
        With Description
      </div>
    </div>
  </div>
</div>

<div class="ui-box hidden">
  <div class="--top">
    <div class="ui-titlepair">
      <h2 class="--title">Tables (Todo)</h2>
      <span class="--description">
        This is still a work in progress and will take some time to complete
      </span>
    </div>
  </div>
  <table class="ui-table">
    <thead>
      <tr>
        <th>First Name</th>
        <th>Last Name</th>
        <th>Email</th>
        <th></th>
        <th></th>
        <th></th>
        <th></th>
        <th></th>
        <th></th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>John</td>
        <td>Doe</td>
        <td>John</td>
        <td>Doe</td>
        <td>John</td>
        <td>Doe</td>
        <td>John</td>
        <td>Doe</td>
        <td>John</td>
        <td>Doe</td>
      </tr>
      <tr>
        <td>John</td>
        <td>Doe</td>
        <td>John</td>
        <td>Doe</td>
        <td>John</td>
        <td>Doe</td>
        <td>John</td>
        <td>Doe</td>
        <td>John</td>
        <td>Doe</td>
      </tr>
    </tbody>
  </table>
</div>


<!-- endregion examples -->