# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    The Ember Router maps paths at the end of the URL to specific views within
    the app.  The routes send and manipulate data from the Ember data store via
    the model and actions.
    ```

2.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route campus/boston
    ```

3.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
  {{#link-to 'campus.boston'}}I'M IN LOVE WITH MASSACHUSETTS{{/link-to}}l
    ```

4.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    The first example is a nested route that will display within the products
    template, the second one is not a nested route and will not.
    ```

5.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    (I'm assuming we have a larger block in a parent route calling something like
    {{#each model as |movie|}}), we would call this as {{movie.id}}.
    ```

6.  Inside a template, how do we reference data provided by a Route?

    ```md
    We use the model - typically we're doing this in an
    {{#each model as |resource|}} block, and then calling {{resource.attr}} on.
    ```
