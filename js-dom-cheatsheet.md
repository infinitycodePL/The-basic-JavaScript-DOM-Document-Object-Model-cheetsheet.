## The basic JavaScript DOM (Document Object Model) cheetsheet.

I build this document based on JavaScript DOM Crash Course by Traversy Media. I also recommend this channel as a great resource for everyone who learns coding.
https://www.youtube.com/channel/UC29ju8bIPH5as8OGnQzwJyA

Maybe this document is not a real cheat sheet but I created just for own purpose. I like to make notes because it helps me to learn fast and better understanding :

### EXAMINE THE DOCUMENT OBJECT

### console.dir(document);
> Displays an interactive list of the properties of the specified JavaScript object. The output is presented as a hierarchical listing with disclosure triangles that let you see the contents of child objects.
>
> In other words, console.dir is the way to see all the properties of specified javascipt object in console by which developer can easily get the properties of object
>
> https://developer.mozilla.org/en-US/docs/Web/API/Document/dir

### console.log(document.domain);
> Gets/sets the domain portion of the origin of the current document
>
> https://developer.mozilla.org/en-US/docs/Web/API/Document/domain

### console.log(document.URL);
> The URL read-only property of the Document interface returns the document location as a string.
>
>https://developer.mozilla.org/en-US/docs/Web/API/Document/URL

### console.log(document.title);
> Gets or sets the title of the document.
>
>https://developer.mozilla.org/en-US/docs/Web/API/Document/title

### console.log(document.doctype);
> Returns the Document Type Declaration (DTD) associated with current document.
>
> https://developer.mozilla.org/en-US/docs/Web/API/Document/doctype

### console.log(document.head);
> Returns the __head__ element of the current document. If there are more than one __head__ elements, the first one is returned.
>
> https://developer.mozilla.org/en-US/docs/Web/API/Document/head

### console.log(document.body);
> Returns the __body__ or __frameset__ node of the current document, or null if no such element exists.
>
>https://developer.mozilla.org/en-US/docs/Web/API/Document/body

### console.log(document.all);
> Provides access to all elements in the document. This is a legacy, non-standard property and should not be used

### console.log(document.all[10]);
    document.all[10].textContent = 'Hello';

### console.log(document.forms[0]);
> The Document property forms returns a collection (an HTMLCollection) listing all the __form__ elements contained by the document.

### console.log(document.links);
> The links property returns a collection of all __area__ elements and __a__ elements in a document with a value for the href attribute.
>
> https://developer.mozilla.org/en-US/docs/Web/API/Document/links

### console.log(document.images);
> The Document object's images property returns a collection of the images in the current HTML document.
>
> https://developer.mozilla.org/en-US/docs/Web/API/Document/images
___

### GETELEMENTBYID('')

> The Document method getElementById() returns an Element object representing the element whose id property matches the specified string. Since element IDs are required to be unique if specified, they're a useful way to get access to a specific element quickly.
>
> https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById

    console.log(document.getElementById('header-title'));
    var headerTitle = document.getElementById('header-title');
    var header = document.getElementById('main-header');
    console.log(headerTitle);
    headerTitle.textContent = 'Hello';
    headerTitle.innerText = 'Goodbye';
    console.log(headerTitle.innerText);
    headerTitle.innerHTML = '<h3>Hello</h3>';
    header.style.borderBottom = 'solid 3px #000';
___

### GETELEMENTSBYCLASSNAME('')
> The Element method getElementsByClassName() returns a live HTMLCollection which contains every descendant element which has the specified class name or names.
>
> https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByClassName

    var items = document.getElementsByClassName('list-group-item');
    console.log(items);
    console.log(items[1]);
    items[1].textContent = 'Hello 2';
    items[1].style.fontWeight = 'bold';
    items[1].style.backgroundColor = 'yellow';
___

### GETELEMENTSBYTAGNAME('')
> The Element.getElementsByTagName() method returns a live HTMLCollection of elements with the given tag name. The subtree underneath the specified element is searched, excluding the element itself. The returned list is live, meaning that it updates itself with the DOM tree automatically. Consequently, there is no need to call several times Element.getElementsByTagName() with the same element and arguments.
>
> https://developer.mozilla.org/en-US/docs/Web/API/Element/getElementsByTagName

    var li = document.getElementsByTagName('li');
    console.log(li);
    console.log(li[1]);
    li[1].textContent = 'Hello 2';
    li[1].style.fontWeight = 'bold';
    li[1].style.backgroundColor = 'yellow';
___

### QUERYSELECTOR('')
> Returns the first element that is a descendant of the element on which it is invoked that matches the specified group of selectors.
>
> https://developer.mozilla.org/en-US/docs/Web/API/Element/querySelector

    var header = document.querySelector('#main-header');
    header.style.borderBottom = 'solid 4px #ccc';

    var input = document.querySelector('input');
    input.value = 'Hello World'

    var submit = document.querySelector('input[type="submit"]');
    submit.value="SEND"

    var item = document.querySelector('.list-group-item');
    item.style.color = 'red';

    var lastItem = document.querySelector('.list-group-item:last-child');
    lastItem.style.color = 'blue';

    var secondItem = document.querySelector('.list-group-item:nth-child(2)');
    secondItem.style.color = 'coral';

### QUERYSELECTORALL('')
> The Element method querySelectorAll() returns a static (not live) NodeList representing a list of the document's elements that match the specified group of selectors.

    var titles = document.querySelectorAll('.title');

    console.log(titles);
    titles[0].textContent = 'Hello';

    var odd = document.querySelectorAll('li:nth-child(odd)');
    var even= document.querySelectorAll('li:nth-child(even)');

    for(var i = 0; i < odd.length; i++){
    odd[i].style.backgroundColor = '#f4f4f4';
    even[i].style.backgroundColor = '#ccc';
    }

## TRAVERSING THE DOM

### parentNode
> The ParentNode mixin contains methods and properties that are common to all types of Node objects that can have children. It's implemented by Element, Document, and DocumentFragment objects.
>
> https://developer.mozilla.org/en-US/docs/Web/API/ParentNode

    console.log(itemList.parentNode);
    itemList.parentNode.style.backgroundColor = '#f4f4f4';
    console.log(itemList.parentNode.parentNode.parentNode);

### parentElement
    console.log(itemList.parentElement);
    itemList.parentElement.style.backgroundColor = '#f4f4f4';
    console.log(itemList.parentElement.parentElement.parentElement);

### childNodes
    console.log(itemList.childNodes);

    console.log(itemList.children);
    console.log(itemList.children[1]);
    itemList.children[1].style.backgroundColor = 'yellow';

### FirstChild
    console.log(itemList.firstChild);

### firstElementChild
    console.log(itemList.firstElementChild);
    itemList.firstElementChild.textContent = 'Hello 1';

### lastChild
    console.log(itemList.lastChild);

### lastElementChild
    console.log(itemList.lastElementChild);
    itemList.lastElementChild.textContent = 'Hello 4';

### nextSibling
    console.log(itemList.nextSibling);

### nextElementSibling
    console.log(itemList.nextElementSibling);

### previousSibling
    console.log(itemList.previousSibling);

### previousElementSibling
    console.log(itemList.previousElementSibling);itemList.previousElementSibling.style.color = 'green';

## createElement
> In an HTML document, the document.createElement() method creates the HTML element specified by tagName, or an HTMLUnknownElement if tagName isn't recognized.


### Create a div
    var newDiv =  document.createElement('div');

### Add class
    newDiv.className= 'hello';

### Add id
    newDiv.id = 'hello1';

### Add attr
    newDiv.setAttribute('title', 'Hello Div');

### Create text node
    var newDivText = document.createTextNode('Hello World');

### Add text to div
    newDiv.appendChild(newDivText);

    var container = document.querySelector('header .container');
    var h1 = document.querySelector('header h1');

    console.log(newDiv);

    newDiv.style.fontSize = '30px';

    container.insertBefore(newDiv, h1);

## EVENTS
> DOM Events are sent to notify code of interesting things that have taken place. Each event is represented by an object which is based on the Event interface, and may have additional custom fields and/or functions used to get additional information about what happened. Events can represent everything from basic user interactions to automated notifications of things happening in the rendering model.
>
> This article offers a list of events that can be sent; some are standard events defined in official specifications, while others are events used internally by specific browsers; for example, Mozilla-specific events are listed so that add-ons can use them to interact with the browser.
>
> https://developer.mozilla.org/en-US/docs/Web/Events

    var button = document.getElementById('button').addEventListener('click', buttonClick);

    function buttonClick(e){
    console.log('Button clicked');
    document.getElementById('header-title').textContent = 'Changed';
    document.querySelector('#main').style.backgroundColor = '#f4f4f4';
    console.log(e);

    console.log(e.target);
    console.log(e.target.id);
    console.log(e.target.className);
    console.log(e.target.classList);
    var output = document.getElementById('output');
    output.innerHTML = '<h3>'+e.target.id+'</h3>';

    console.log(e.type);

    console.log(e.clientX);
    console.log(e.clientY);

    console.log(e.offsetX);
    console.log(e.offsetY);

    console.log(e.altKey);
    console.log(e.ctrlKey);
    console.log(e.shiftKey);
    }

    var button = document.getElementById('button');
    var box = document.getElementById('box');

### button.addEventListener('click', runEvent);
### button.addEventListener('dblclick', runEvent);
### button.addEventListener('mousedown', runEvent);
### button.addEventListener('mouseup', runEvent);

### box.addEventListener('mouseenter', runEvent);
### box.addEventListener('mouseleave', runEvent);

### box.addEventListener('mouseover', runEvent);
### box.addEventListener('mouseout', runEvent);

### box.addEventListener('mousemove', runEvent);

### itemInput.addEventListener('keydown', runEvent);
### itemInput.addEventListener('keyup', runEvent);
### itemInput.addEventListener('keypress', runEvent);

### itemInput.addEventListener('focus', runEvent);
### itemInput.addEventListener('blur', runEvent);

### itemInput.addEventListener('cut', runEvent);
### itemInput.addEventListener('paste', runEvent);

### itemInput.addEventListener('input', runEvent);

### select.addEventListener('change', runEvent);
### select.addEventListener('input', runEvent);

### form.addEventListener('submit', runEvent);

    function runEvent(e){
    e.preventDefault();
    console.log('EVENT TYPE: '+e.type);

    console.log(e.target.value);
    document.getElementById('output').innerHTML = '<h3>'+e.target.value+'</h3>';

    output.innerHTML = '<h3>MouseX: '+e.offsetX+' </h3><h3>MouseY: '+e.offsetY+'</h3>';

    document.body.style.backgroundColor = "rgb("+e.offsetX+","+e.offsetY+", 40)";
    }
