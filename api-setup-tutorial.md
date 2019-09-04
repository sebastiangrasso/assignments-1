**CMSI 370** Interaction Design, Fall 2019

# Assignment 0919b

Conceptually, this assignment is integral to the [front-end design and white paper](https://github.com/lmu-cmsi370-fall2019/assignments/blob/master/front-end-design.md), but its content and tasks are sufficiently distinct that they work better as a separate deliverable.

In order to turn your front end design into a reality, you will need to learn how to work with the web service API that provides its functionality (the _utility_, in Nielsen’s terms). For many of you, this will be your first time doing this, so this assignment is meant to give you some structure for learning how to do it.

## Background Reading
A lot of information is available on the web for how to interact with web services, but to save time, the most relevant information has been gathered into a primer that accompanies the assignment repository, so most importantly, [read that primer](./web-service-api-primer.md). The how-to on this document is meant to be self-contained, so reading this and  following along the supplied walk-throughs serves as your best starting point.

After that, performing web searches on how to use specific technologies (_curl_, Postman, `window.fetch`) should help supplement the information here. Some starting points, hosted by the home sites of these technologies:
* Postman: https://learning.getpostman.com/docs/postman/launching_postman/sending_the_first_request/
* _curl_: https://curl.haxx.se/docs/manpage.html
* `window.fetch`: https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch (`window.fetch` is a browser standard so Mozilla Developer Network is a good site for this type of documentation)

## For Submission: API Setup/Tutorial Document
For this part of the initial design and preparation work for your front end, acquire some hands-on experience with the web service API(s) that your front end will use. The intent of this assignment is to have you:
* Learn how to send requests and interpret responses to and from a web service
* Document that you _did_ learn how to do this and practiced this enough to be ready for implementation
* Identify potential issues with your chosen web service API(s) so that we can take steps to resolve them

To accomplish this, do the following:
1. Fully read [A Primer on Interacting with Web Service APIs](./web-service-api-primer.md)
2. Read the documentation of the web service(s) you intend to use for your front end
3. If needed, sign up for an account with said web service(s)
4. Use _curl_ or Postman (or both) to send requests to the web service(s)
5. Use `window.fetch` to send requests to the web service(s)
    * Note how you may choose between _curl_ or Postman for initial practice, but you _must_ also use `window.fetch`
    * The reason for this is that `window.fetch` runs within a web browser, and there are aspects of interacting with a web service API that are specific to their use in a browser (e.g., [CORS](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing))
    * Another reason is that those of you who will build a web app for your front end will be using `window.fetch` in the app code itself—thus, this assignment serves as a preview for that
6. Learn to read and understand the responses that you get back
7. Write up a report showing that you sent the requests that you plan to use and can point out the data that will be needed by your front end within their responses
    * Many web service APIs will give you an API key or other credentials in order to use them—normally, these should _not_ be posted on any websites or repositories, but because your assignments are private and this information will be needed for verification and grading, make an exception in this case and make sure to provide this information in your report
8. _Include examples of your own requests and responses_ in the document via screenshots
    * This is another reason for making an exception with supplying API keys or credentials—screenshots of real requests and responses will have this information anyway
    * Genuinely perform these requests yourself, and don’t just appropriate screenshots from the documentation or the web, nor ask someone else to do it and grab their screenshots—not only is this academically dishonest, but it will be problematic later when you actually start to implement your front end

### General Outline
Start your report with an “Executive Summary” section—essentially a TL;DR for the overall exercise. This section should give the reader a general sense for how things went.

Your report should then include the following information _for every web service function_ that you plan to use in your front end. In other words, most reports should have three (3) sections that all look like this:
1. Brief explanation of the web service function/endpoint
2. Documentation/screenshots that you can send requests for this endpoint in Postman or _curl_
3. Documentation/screenshots that you can send requests for this endpoint with `window.fetch` in a web browser
4. Documentation/screenshots of the responses that you receive
5. Brief explanation/navigation of the responses to point out the information that you plan to use
    * For JSON responses (which will be what most web services return), use a JavaScript expression rooted at the response (because it’s JSON after all; e.g., `response.data[0].images.fixed_height.url`)
6. If applicable, document any issues or errors that you encountered, particularly with `window.fetch`
    * It is very possible that you will encounter success with Postman or _curl_ but not with `window.fetch`—these, in particular, are the issues that we want to get a handle on
    * If you encounter problems with _all_ mechanisms for making requests, then this is most likely “pilot error” (i.e., the tools aren’t being used in a way that matches the web service API specification) or a serious server reliability issue—for the former, resolving the issue is a matter of figuring things out; for the latter, this might be a signal that you are better off with a different (more reliable) web service
    * If no errors are encountered at all _explicitly say so_ in order to be clear that you didn’t just forget to report them

If your front end will need more than three (3) distinct web service functions, you may choose any three to report back on. Note it will still be beneficial for you to try out _all_ of the web service functions, just in case a problematic one is lurking among them outside of the three that you will document in this assignment.

### How to Turn it In
Commit the tutorial in this repository under the filename _api-setup-tutorial.md_.

## Specific Point Allocations
This assignment fits specific subsets of outcomes _3a_, _3b_, _4a_, and _4c_ to _4f_ in the [syllabus](http://dondi.lmu.build/fall2019/cmsi370/cmsi370-fall2019-syllabus.pdf), and will mainly be scored according to the degree to which the content delivered aligns with the content requested by the instructions. Outcomes _3a_ and _3b_ apply here to the ability to work at the boundary where usability meets utility, which is what the web service calls represent. Outcome _4a_ applies to how correctly the tools are used (where `window.fetch` also counts as “syntactically correct, functional code”). For this particular assignment, graded categories are as follows:

| Category | Points | Outcomes |
| -------- | -----: | -------- |
| Executive Summary | 5 points | _3a_, _3b_, _4d_ |
| Web Service Reports | 25 points each, 75 points total | |
| • Brief explanation | 2 points | _4d_ |
| • Postman or _curl_ report and screenshots | 5 points | _3a_, _3b_, _4a_, _4d_ |
| • `window.fetch` report and screenshots | 5 points | _3a_, _3b_, _4a_, _4d_ |
| • Response report and screenshots | 5 points | _3a_, _4d_ |
| • Response navigation | 5 points | _3a_, _4d_ |
| • Error report | 3 points | _4d_ |
| Writing | deduction only | _4c_ |
| Version Control | deduction only | _4e_ |
| Punctuality | deduction only | _4f_ |
| **Total** | **80** |

As a writing assignment, outcome _4c_ is interpreted here as writing clarity and correctness instead of code readability. The last three graded categories are “deduction only,” meaning that you will only get points taken off if there are significant issues with those categories. Such issues include but are not limited to: unclear, unproofread, or erroneous writing (_4c_), insufficiently granular or unmessaged commits (_4e_), and late commits (_4f_).
