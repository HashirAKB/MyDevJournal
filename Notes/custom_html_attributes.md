```markdown
# Examples of Using data-* Attributes in HTML and Accessing Them in JavaScript

## Variation 1:

```html
<div class="user" data-user-id="123" data-user-name="John Doe" data-user-age="30">
    <!-- User content -->
</div>
```

In JavaScript:

```javascript
const userDiv = document.querySelector('.user');
const userId = userDiv.dataset.userId; // "123"
const userName = userDiv.dataset.userName; // "John Doe"
const userAge = userDiv.dataset.userAge; // "30"
```

## Variation 2:

```html
<button class="product" data-product-id="ABC123" data-product-price="19.99" data-product-category="electronics">
    Add to Cart
</button>
```

In JavaScript:

```javascript
const productBtn = document.querySelector('.product');
const productId = productBtn.dataset.productId; // "ABC123"
const productPrice = productBtn.dataset.productPrice; // "19.99"
const productCategory = productBtn.dataset.productCategory; // "electronics"
```

## Variation 3:

```html
<li class="item" data-id="1" data-name="Item 1" data-quantity="3">
    <!-- Item content -->
</li>
```

In JavaScript:

```javascript
const itemLi = document.querySelector('.item');
const itemId = itemLi.dataset.id; // "1"
const itemName = itemLi.dataset.name; // "Item 1"
const itemQuantity = itemLi.dataset.quantity; // "3"
```

## Variation 4:

```html
<a href="#" class="link" data-analytics-id="9876" data-analytics-action="click" data-analytics-category="navigation">
    Home
</a>
```

In JavaScript:

```javascript
const linkA = document.querySelector('.link');
const analyticsId = linkA.dataset.analyticsId; // "9876"
const analyticsAction = linkA.dataset.analyticsAction; // "click"
const analyticsCategory = linkA.dataset.analyticsCategory; // "navigation"
```

These examples illustrate how you can use `data-*` attributes to store custom data in HTML elements and access them in JavaScript using the `dataset` property.
```