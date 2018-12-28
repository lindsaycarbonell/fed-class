# Which ruleset will win?
_taken from: [Sarah Hudson's SlideShare](https://www.slideshare.net/shudson4/charlotte-fed-css-inheritance-and-specificity)_

1) Given HTML: 
    ```
    <footer class="main-footer">
        <a href="#about-us" class="navigation--link site-map--link">About Us</a>
    </footer>
    ```
    And CSS: 
    ```
    .main-footer a {
        color: white;
    }
    a.site-map--link {
        color: darkblue;
    }
    a.navigation--link {
        color: skyblue;
    }
    ```
    What will the link color be?

    A: Skyblue.

2) Given HTML: 
    ```
    <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Contact</a></li>
    </ul>
    ```
    And CSS: 
    ```
    li > a { color: green; }
    li a { color: brown; }
    ```
    What will the link color be?

    A: It will be brown because the sleectors are euqal weight; it chooses the last one. It's important to note that combinators such as > and ~ have no weigth on specificity. They're a part of inheitance instead, ensuring we only grab the a tags directly under our li tags, but we don't apply the declarations to a tags which are in divs in li elements.

3) Given HTML: 
    ```
    <aside id="sidebar">
        <section id="salads">
            <ul>
                <li><a href="#">Cobb Salad</a></li>
            </ul>
        </section>
    </aside>

    ```
    And CSS:
    ```
    aside#sidebar a {
        background-color: yellow;
    }
    aside#sidebar a[href="#"] {
        background-color: lightgreen;
    }
    section#salads li a {
        background-color: aliceblue;
    }
    ```
    What will the link background-color be?

    A: The background will be light green. This is because the attribute selector adds more specificity than the other two selectors.

4) Given HTML: 
    ```
    <section id="intro-text">
        <p>Lorem ipsum</p>
    </section>
    ```
    Given CSS: 
    ```
    section#intro-text {
        color: red!important;
    }
    p {
        color: darkgrey;
    }
    ```
    A: The paragraph will be darkgrey. Specificity is not inherited. Since we're using the parent element as a selector, it will apply to the parent element, but selecting "p" is more sepcific to the "p" tag than the parent's selector.

5)  Given HTML: 
    ```
    <html>
        <body>
            <main>
                <section>
                    <header>
                        <h2>
                            <div><span><span><span><span class="orange-text">weeee</span></span></span></span></div>
                        </h2>
                    </header>
                </section>
            </main>
        </body>
    </html>
    ```
    And CSS: 
    ```
    html body main section header h2 div span span span span {
        color: purple;
    }
    .orange-text {
        color: orange;
    }
    ```
    What color will the text of the `<span>` wrapped around the text be?

    A: Class selectors always beat out element selectors, so the text will be orange.

6) Given HTML: 
    ```
    <section>
        <header>
            <h2 style="color: red;" class="test-important-text">Test</h2>
        </header>
    </section>
    ```
    Given CSS: 
    ```
    .test-important-text {
        color: purple !important;
    }
    ```
    What color will the text be?
    A: Purple. !important breaks all other specificity rules, including inline styles (In fact, important tags are the only way to override inline styles).

