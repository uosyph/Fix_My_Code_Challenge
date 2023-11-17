# 0x00 Challenge

This repository contains a fixed version of the code challenge from the original [0x01-Fix_My_Code_Challenge](https://github.com/alx-tools/0x01-Fix_My_Code_Challenge) repository.

## Changes Made

### [status_server/api/v1/views/index.py](status_server/api/v1/views/index.py)

The issue with the original Python code is that it defined a Flask route decorator as `@app_views.route('/api/v1/status', methods=['GET'], strict_slashes=False)`, but it was incorrect and caused a bug.

To fix this bug, the code was modified by changing the route decorator to `@app_views.route('/status', methods=['GET'], strict_slashes=False)`. By removing the `/api/v1` prefix from the route, the bug was resolved and the endpoint is now accessible at `/status` instead of `/api/v1/status`.

This fix ensures that the Flask application correctly handles requests to the `/status` route, providing the desired functionality.

Overall, the modified code addresses the bug by adjusting the route decorator, ensuring the proper behavior of the application.

### [square.py](square.py)

The issue with the original Python code was that there was a bug in the "area_of_my_square" method, which incorrectly calculated the area by squaring the width instead of multiplying the width and height. Additionally, the code lacked proper formatting and naming conventions. The class name "square" should have been capitalized as "Square" and the method names should have followed the standard Python naming convention.

To address these issues, the fixed code first resolves the bug in the "area_of_my_square" method by modifying it to correctly calculate the area by multiplying the width and height attributes. Then, the code is properly formatted and named. The class is now named "Square" and the method names follow the standard Python naming convention.

Overall, the fixed code now accurately calculates the square's area and is properly formatted and named, ensuring code readability and maintainability.

### [user.py](user.py)

The issue with the original Python code is that it defines a `User` class with an `email` attribute. The `email` attribute has a setter method that checks if the provided value is a string and raises a `TypeError` if it's not. The code also has a getter method for the `email` attribute.

To fix this, the corrected code first changes the order of the getter and setter methods for the `email` attribute. In the original code, the setter method was defined before the getter method, which caused a `NameError` when trying to access the `email` attribute. By switching the order, the code now correctly sets and gets the `email` attribute.

Overall, the fixed code ensures that the `email` attribute can be properly set and retrieved in the `User` class, resolving the issues with the original code.

### [blog/](blog/)

#### [app/controllers/posts_controller.rb](blog/app/controllers/posts_controller.rb)

- The `before_action` filter is modified to include the `:show` action in the exceptions list. Previously, the `:show` action was not excluded from the `authenticate_user!` filter, which means it would require authentication before accessing the post details. With this change, the `:show` action can now be accessed without authentication.

- The `@posts` variable assignment is updated in the controller. Previously, it retrieved all posts from the database and ordered them by the `created_at` attribute in descending order. Now, it only fetches posts where the `online` attribute is set to `true` and orders them by `created_at` in descending order. This change ensures that only online posts are displayed.

- The update mechanism for the `@post` object is modified. Previously, it updated the `title` and `body` attributes of the `@post` object based on the parameters received. Now, it also updates the `online` attribute if it is included in the permitted parameters. This change allows for updating the online status of a post along with the title and body.

- The parameters used for permitting attributes in the `post` object are updated. Previously, only the `:title` and `:body` attributes were permitted using `params.require(:post).permit(:title, :body)`. Now, the `:online` attribute is also included in the permitted parameters using `params.require(:post).permit(:title, :body, :online)`.

### [react-blog/](react-blog/)

#### [src/actions/AllPostActions.js](react-blog/src/actions/AllPostActions.js)

- There is a typo in the function call `this.actions.updatePosts()`. The word "Psots" should be corrected to "Posts" to match the correct function name.

- The calculation of the `start` variable is modified. Previously, it used the modulo operator `%` to calculate the value based on the `pageNum`. Now, it directly multiplies the `pageNum` with the `config.itemsPerPage` value. This change ensures that the correct starting index is calculated for pagination.

- There is a typo in the `request.get()` function call. The word "reqeust" should be corrected to "request" to match the correct function name.

- The function call `self.actions.update_numberOfPosts()` is modified. Previously, it used an underscore in the function name, but now it uses camel case without the underscore. This change ensures consistency in the function naming convention.

- Modified in the function call `self.actions.update_numberOfPosts()`. Previously, it used an underscore in the function name, but now it uses camel case without the underscore. This change ensures consistency in the function naming convention and aligns with the correct function name. The updated code is `self.actions.updateNumberOfPosts(state.numberOfPosts);`.

#### [src/actions/SinglePostActions.js](react-blog/src/actions/SinglePostActions.js)

- In this code snippet, there is a change in the for loop declaration. Previously, the loop used the incorrect syntax `for(const i=0; i<includes.length; i++)`. The correct syntax is updated to `for(let i=0; i<includes.length; i++)`. This change ensures that the loop variable `i` is properly declared with the `let` keyword and the loop condition is correctly specified as `i<includes.length`, indicating that the loop should continue as long as `i` is less than the value `<includes.length`.

#### [src/components/Header.jsx](react-blog/src/components/Header.jsx)

- The line `<NavBrand>Link to={/}>React Blog</Link></NavBrand>` has been updated to `<NavBrand><Link to={/}>React Blog</Link></NavBrand>`. This change fixes the incomplete link syntax and adds the missing opening tag for the `Link` component.

#### [src/components/PostPreview.jsx](react-blog/src/components/PostPreview.jsx)

- The line `<a href={'/post/ + this.props.post.id + /'+this.props.post.slug} className="single-post" onClick={this.loadPost}>` has been modified to `<a href={'/post/' + this.props.post.id +'/'+this.props.post.slug} className="single-post" onClick={this.loadPost}>`. This change fixes the missing quotation marks around the path and adds the necessary slashes to correctly construct the href attribute.

## Acknowledgements

The original code challenges were part of the [0x01-Fix_My_Code_Challenge](https://github.com/alx-tools/0x01-Fix_My_Code_Challenge) repository.
