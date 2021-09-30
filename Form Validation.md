# Form Validation

## [What is form validation?](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#what_is_form_validation "Permalink to What is form validation?")

Go to any popular site with a registration form, and you will notice that they provide feedback when you don't enter your data in the format they are expecting. You'll get messages such as:

-   "This field is required" (You can't leave this field blank).
-   "Please enter your phone number in the format xxx-xxxx" (A specific data format is required for it to be considered valid).
-   "Please enter a valid email address" (the data you entered is not in the right format).
-   "Your password needs to be between 8 and 30 characters long and contain one uppercase letter, one symbol, and a number." (A very specific data format is required for your data).

This is called  **form validation**. When you enter data, the browser and/or the web server will check to see that the data is in the correct format and within the constraints set by the application. Validation done in the browser is called  **client-side**  validation, while validation done on the server is called  **server-side**  validation. In this chapter we are focusing on client-side validation.

If the information is correctly formatted, the application allows the data to be submitted to the server and (usually) saved in a database; if the information isn't correctly formatted, it gives the user an error message explaining what needs to be corrected, and lets them try again.

We want to make filling out web forms as easy as possible. So why do we insist on validating our forms? There are three main reasons:

-   **We want to get the right data, in the right format.** Our applications won't work properly if our users' data is stored in the wrong format, is incorrect, or is omitted altogether.
-   **We want to protect our users' data**. Forcing our users to enter secure passwords makes it easier to protect their account information.
-   **We want to protect ourselves**. There are many ways that malicious users can misuse unprotected forms to damage the application (see  [Website security](https://developer.mozilla.org/en-US/docs/Learn/Server-side/First_steps/Website_security)).  
    
    **Warning::**  Never trust data passed to your server from the client. Even if your form is validating correctly and preventing malformed input on the client-side, a malicious user can still alter the network request.
    

## [Different types of client-side validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#different_types_of_client-side_validation "Permalink to Different types of client-side validation")

There are two different types of client-side validation that you'll encounter on the web:

-   **Built-in form validation**  uses HTML5 form validation features, which we've discussed in many places throughout this module. This validation generally doesn't require much JavaScript. Built-in form validation has better performance than JavaScript, but it is not as customizable as JavaScript validation.
-   **JavaScript**  validation is coded using JavaScript. This validation is completely customizable, but you need to create it all (or use a library).

## [Using built-in form validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#using_built-in_form_validation "Permalink to Using built-in form validation")

One of the most significant features of  [HTML5 form controls](https://developer.mozilla.org/en-US/docs/Learn/Forms/HTML5_input_types)  is the ability to validate most user data without relying on JavaScript. This is done by using validation attributes on form elements. We've seen many of these earlier in the course, but to recap:

-   `[required](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/required)`: Specifies whether a form field needs to be filled in before the form can be submitted.
-   `[minlength](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/minlength)`  and  `[maxlength](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/maxlength)`: Specifies the minimum and maximum length of textual data (strings)
-   `[min](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/min)`  and  `[max](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/max)`: Specifies the minimum and maximum values of numerical input types
-   `type`: Specifies whether the data needs to be a number, an email address, or some other specific preset type.
-   `[pattern](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/pattern)`: Specifies a  [regular expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)  that defines a pattern the entered data needs to follow.

If the data entered in a form field follows all of the rules specified by the above attributes, it is considered valid. If not, it is considered invalid.

When an element is valid, the following things are true:

-   The element matches the  [`:valid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:valid)  CSS pseudo-class, which lets you apply a specific style to valid elements.
-   If the user tries to send the data, the browser will submit the form, provided there is nothing else stopping it from doing so (e.g., JavaScript).

When an element is invalid, the following things are true:

-   The element matches the  [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)  CSS pseudo-class, and sometimes other UI pseudo-classes (e.g.,  [`:out-of-range`](https://developer.mozilla.org/en-US/docs/Web/CSS/:out-of-range)) depending on the error, which lets you apply a specific style to invalid elements.
-   If the user tries to send the data, the browser will block the form and display an error message.



## [Built-in form validation examples](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#built-in_form_validation_examples "Permalink to Built-in form validation examples")

In this section, we'll test out some of the attributes that we discussed above.

### [Simple start file](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#simple_start_file "Permalink to Simple start file")

Let's start with a simple example: an input that allows you to choose whether you prefer a banana or a cherry. This example involves a simple text  [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)  with an associated  [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)  and a submit  [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button). Find the source code on GitHub at [fruit-start.html](https://github.com/mdn/learning-area/blob/master/html/forms/form-validation/fruit-start.html) and a live example below.




### [The required attribute](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#the_required_attribute "Permalink to The required attribute")

The simplest HTML5 validation feature is the  `[required](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/required)`  attribute. To make an input mandatory, add this attribute to the element. When this attribute is set, the element matches the  [`:required`](https://developer.mozilla.org/en-US/docs/Web/CSS/:required)  UI pseudo-class and the form won't submit, displaying an error message on submission when the input is empty. While empty, the input will also be considered invalid, matching the  [`:invalid`](https://developer.mozilla.org/en-US/docs/Web/CSS/:invalid)  UI pseudo-class.
