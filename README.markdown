# xmlbuilder.js

An xml builder in Javascript inspired by Ruby's Builder, Markaby, and Erector.

## Example Usage

    var b = new XmlBuilder({binding: this})
    with(b) {
      html(function() {
        head(function() {
          title("My Personal Web Page")
        })
        body(function() {
          h1("Hey You! Welcome to my web page!!!")
          div({id: "page-content", 'class': "my-class"}, function() {
            p("I'm so glad you could visit &amp; am happy you are reading this.")
            textNode("I 'dig' turtles & stuff. I go to the pet store > 1 time a week.")
            p(function() {
              text("In the mean time, check "); a("this", {href: "/snazzy/flash-page.html"}); text(" out.")
            });
          })
        })
      })
    }
    b.toString()