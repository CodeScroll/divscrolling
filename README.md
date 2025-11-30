# divscrolling
A simple jQuery scrolling for representation type web page. After a search i see that i have to load and read strange, ~ big libraries for achieve a "per div scroll". So i write a piece of code to implent this". You can add more divs but you need to add the divs id to sections variable.

Otherwise you can collect the ids with preferred way of class selection like $('.scrolldiv').each(function(){ sections.push($(this).attr('data-id'));});

How is it working.

<b>isScrollToFinished()</b> function , is the starter function. "when the page goes to top(Y=0)". Will start the handler for the scrolling.
on page load. it will go to top with <b>window.scrollTo(0,0);</b>

<b>onScroll()</b> = "when the window scrolling up or down". when scrolling up, will call the previous section(from section 3 to section 2). and will execute the 

<b>scrollToSection()</b> function. this function just animate to scroll to the target div. additionally its the "guard" updater of "isScrolling" variable. when the animation starting will set this to true. when it finished to false.

respectively for down scrolling. There it will executed the <b>nextSection()</b>

to disable it for mobile diveces add this.

<script>

    function isMobile() {
      return /Android|iPhone|iPad|iPod|Opera Mini|IEMobile|WPDesktop|BlackBerry/i.test(
        navigator.userAgent
      );
    }
    
    const isMobileTwo = window.matchMedia("(any-pointer:coarse)").matches;
    if (!isMobile() && !isMobileTwo) {
        isScrollToFinished();
        window.scrollTo(0,0);
    }
</script>
