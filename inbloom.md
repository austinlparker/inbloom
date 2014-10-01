# inBloom Post Mortem 

You can't throw a virtual rock without hitting someone talking about the transformative powers of "big data". (Incidentally, you can't throw a real rock without hitting someone talking about the transformative powers of "big data" if you're walking around the Informatics department, either). There's been [a few][3] [slight][4] [incidents][5] in the past year that raise the spectre of souless corporate overlords collecting reams of quantified information about people and manipulating or selling it to the highest bidder.

Admittedly, when [inBloom was dreamt up in 2011][1], we were in a more innocent, Snowden-free time. Never the less, over $100 million dollars later, inBloom lays fallen; Supposedly, a victim of concerns about student data privacy - although its supporters would argue that it was slain by neo-luddites unable or unwilling to grasp their vision of a brighter and more connected education that involved a lot of students using iPads.

What happened? inBloom and its originator, the [Shared Learning Collaborative][1] were designed by top educators and administrators. Funding was provided as grants, not as venture capital with profit expectation. [Douglas Levin, executive director of the State Educational Technology Directors Association][2] had this to say upon the death of inBloom:
>"While perhaps ahead of its time, the inBloom vision--and the tools inBloom built to realize it--remain critically important for the K-12 sector to build upon in the future ... I certainly hope that others will step up to fill the void that inBloom will be leaving in its wake."

Of course, inBloom had its detractors, such as [parent activist Leonie Haimson][2], who noted:
>"There are more and more data-mining vendors who, with the help of government officials, foundations, and think tanks, are eager to make money off of student information in the name of "big data" and "personalized" learning, and in the process see parents, if they recognize our existence at all, as ignorant obstacles to their Orwellian plans"

To argue, however, that this is simply a story of concerned parents against technocratic overlords is, I believe, to miss a large point. inBloom was conceived as an [open source product][6], with a community of educators and developers working together to guide the both the implementation and orchestration of the project. I mean, these guys were on _GitHub_, obviously they're open as can b-

![heh][7]

Hm.

## Development

inBloom was primarily interested in creating a distributed, national, data warehouse with a sprawling schema that conformed to educational data frameworks such as the [Learning Registry][8]. The development work for the backend seems to have been developed to the strictures and plan of edSurge/SLC prior to inBloom even being 'a thing'. As noted on [this IMS Global blog post][9], "Open source is not open standards". I would tend to agree, and so would [ESR][10] whose [16 Open Source Development Guidelines][11] were published in the seminal "Cathedral and the Bazaar". There are at least two primary issues I can identify with the software development practices of inBloom - first, the software stack was designed to be a monolithic solution to an already solved problem, and second, community developers were not brought in to the underlying data warehousing application and only offered the ability to write apps on top of the platform that inBloom offered.

#### Mo' Money, Mo' Problems

inBloom was a top-heavy organization. Flush with cash, and with a mandate from administrators at the top of the educational ladder, they set out to build a software product that would remove integration challenges between multiple products. This in and of itself is a noble goal, but there were two issues - first, the impetus was not "Let's solve a problem that needs solving" (violating [OSD 1][11], "Every good work of software starts by scratching a developer's personal itch") but "Let's go ahead and build something that no one is asking for because hey, we got the cash and it's a lot easier to just bully everyone else into getting on our side once we've made the backend". Looking at the [inBloom Products and Services Matrix][12] we can see that their launch applications were not only a bit lacking, all of the effort had gone into creating the data store. Without applications that end-users and other community members can both see and utilize, there was little incentive for participation (violating [OSD 12, 18][11]) which almost certianly touched off the backlash from concerned parents. A better plan, perhaps, would have been to involve both educators at a district or school level in the context of developers and contributors from an earlier point and to focus less on the back-end. This would have both helped in finding "itches to scratch" as well as lead to better initial applications and tools that may have eased adoption.

#### sChemas Rule Everything Around Me, C.R.E.A.M

There's a definite bridge between the issue of 'reinventing the wheel' and 'not bringing in developers early enough'. I'm going to reference a [great piece from Joel Spolsky][13] that kinda gets at it. Joel presents the 'chicken and the egg' problem regarding platforms, and looks at the success of PC-DOS, Windows 3.x, and Windows 95. In summary, he notes that the reason that major platforms were adopted as easily as they were is primarily due to their backwards compatibility with existing applications. inBloom suffered from a similar 'chicken and the egg' problem that was quite self-inflicted. [Note the developer timeline in their jumpstart presentation][14], especially the slides where they discuss what was provided and what wasn't, and when contributions were accepted. inBloom wrote very thin 'example' applications, and didn't provide opportunities to work on underlying schema or data store development. The project was centrally planned from an earlier stage to conform to certain expectations, as I noted above. I'd argue that this is, primarily, a failure of development leadership (violating [OSD 19][11]) by inBloom. By not involving a development community earlier in the process, there was not only a longer lead time for developers to write applications on the platform but the scramble to push out applications meant there was less time to consult with SME (subject matter experts) in education to design those applications.

## Community and Governance

The other great failure of inBloom was the way it managed community engagement and roles. I've already noted that the product appeared to be targeted at leapfrogging existing educational technology vendors and platforms by delivering an omnibus data warehouse. The blame for these decisions, while faults of development, need to lay at the project management and governance board. [The History of inBloom][15] notes that the original SLC alliance was lead by the Council of Chief State School Officers (hereforth CCSSO) and an governance advisory board. Members of this advisory board included educational higher-ups such as the President of the American Federation of Teachers and the Director of what was known as the Innosight Institute - now the [Christensen Institute][16]. 

Let's pause a moment on that last one.

We can thank one Clayton M. Christensen, PhD, for the seminal 1997 text ["The Innovator's Dilemma"][17] which essentially argued that the failure of companies is that they don't make poor decisions, it's that they make the same kind of decisions that have worked for decades and are unable to adapt to changing market and global forces. A popular example is the story of the mainframe computer - IBM, DEC, and others continued to innovate in their field of building and improving on mainframes, because that's what their customer base used. However, they missed the personal computer revolution and were unable to adapt precisely because they didn't recognize the demand from individuals or small businesses who were not in their market.

Thus, MBAs spake unto the world the gospel of 'disruption'.

Christensen bottled lightning with his text and has been riding it since. [Some of his newer work as co-author includes "The Innovative University", "Disrupting Class", and "The Innovator's Prescription"][18] where he argues for the disruption of higher education, public education, and health care - respectively. The word 'disruption' has wormed its way into the lexicon of technology in the most infuriatingly adorable way. Everything is disruptive, now. [Soylent is an open source nutritional drink developed by self-research][19] to 'disrupt' eating food. [washio is a dry cleaning and laundry delivery service][20] that promises to 'disrupt' the act of doing your own fucking laundry by employing legions of 1099 independent contractors who will do it _for you_, so I guess it's really disrupting laundromats. I would be remiss to not include a note about the favorite disruption darling du jour, [Uber, the car sharing service for people who can't do anything without it being an app][22] who is also apparently [disrupting the search trend for 'uber scandal'][21] via their much publicized "dial our competition then ditch the ride" and ["well we don't really employ the drivers so we shouldn't have to do background checks"][23] issues. The word has taken on a farcical tone, preached as a gospel by the YCombinator Class of Whatever adherents and their priest, Paul Graham. It has become a symbol of what is wrong in the tech industry - nay, perhaps the global economy. 

[At least the dumb 'We'll send you rolls of quarters in the mail to do your laundry with' service died. Change machines remain un-disrupted.][24]

With that in mind, I believe it suddenly becomes much more understandable as to why the leadership at inBloom was unable to successfuly meld it into a successful open source project.

#### Shake It Off (privacy concerns, that is)

The primary, and I would argue overriding concern, is that top-down organization was intent on obfuscating and dismissing concerns about data privacy. I'm willing to give them [the benefit of the doubt][25] based on some answers they gave when interrogated about data privacy, but there's a pretty huge hole sitting in their answers.
>inBloom is an independent, nonprofit organization that is committed to keeping its operating costs and service fees low to support sustainable, cost-effective personalized learning. Thanks to initial funding from the Gates Foundation and Carnegie Corporation, *we are able to offer our 9 pilot states and districts the secure data service and Learning Registry Index for free until 2015*. Later in 2013 we will begin working with additional state and district customers, who will *pay a nominal per-student license for our services*. inBloom has done significant cost benefit analysis, and we project that states and districts who invest in three or more personalized learning tools per year will typically save $5–10 per student on application integration costs, easily recouping inBloom’s license fees. *We are also exploring approaches to recover costs from providers who benefit from using our service to serve their customers*.

That last statement, at the least, has a bit of a chilling air to it. I would certainly note that this statement, in its totality, [violates several Open Source Benefits (enforces vendor lock-in, poor organizational audibility, and has licensing costs)][11]. It's also a bit of a weasel response - 'exploring approaches to recover costs from providers who benefit from using our service to serve their customers' has the smack of pay-for-play data mining/analytics or simply advertising profiles. While I'm hardly a maximalist for privacy rights, I'm not sure that educational service companies really should be utilizing a product that is supposedly meant for educational goals to figure out better ways to market milk through a student lifecycle, or for Pearsson to try and sell more textbooks to already cash-strapped districts.

I think there is a very clear and bright line between the overall governance board and decisions such as the above with the overall project. The philosophy of disruption is largely unchallenged, we just naturally assume that everything needs an app and everyone should be advertised to from cradle to grave because it seems to work for Google and Facebook, right? This sort of attitude probably didn't help in terms of outreach to community members who were more interested in a design and governance role, either - either they were locked out of the process by the monolithic initial design and structure, or they were turned off by the seeming nature of inBloom to harvest vast quantities of student data for potentially obscure purposes.

#### It Takes A Nation Of Millions To Hold Us Back

To ruthlessly crib from [Rob Abel][9] again:
>You can have a lot of people around the table, but if they aren’t the right people the net result will probably be wrong.

>Working with the education sector is likely to produce a better result than trying to end-run it. InBloom was an attempt to end-run districts, existing suppliers, and, yes, existing standards organizations like IMS Global.

>“Small” (read:) actionable data is much more important than big data in education.

There's a lot of sturm und drang in the United States about the division of power and responsibility to be parceled between federal, state, district, and local school organizations. We've already noted that inBloom attempted to end-run many of those lower-level entities by starting at the top and orchestrating their leadership and planning around that vision. By rejecting smaller players they not only managed to alienate potential allies, but failed to find support from existing partners in educational technology who were working on open standards. I would note here that this strategy violates several Open Source Benefits - ["Standards based", "Standards setting", and "Emphasizes concepts, not products"][11]. When you start out with the wrong people at the table, who make the appearance of 'end-running' existing structures, you're not going to get a lot of community support from _anyone_ be they educator, developer, parent, or administrator. 

Furthermore, inBloom may have missed the entire point. When your God is Disruption and you are surrounded by its Prophets, how could you not believe? The concepts sound great - heck, even I'll sometimes watch a TED Talk and think that we're all going to be saved by "big data" and African children programming JavaScript - but studies show the best way to close the 'achievement gap' is [simply giving schools more money][26]. [In 2012, Connecticut public schools were underfunded to the tune of *$763 million*][27], while noting that the actual cost gap was much higher due to flawed formula used in calculations. The report noted that it suspected the actual cost was well over $1 billion. When parents are [barraged by ever-increasing costs for public school supplies][28] (up to $350 per child!) in the face of shrinking educational funding, not to mention [record-high college tuition rates][29], skepticism is perhaps an expected response to the idea of throwing money on some pie-in-the-sky "big data" platform. Perhaps Mr. Gates $100 million would have been better utilized by writing a check to extremely impoverished schools in terms of improving educational outcomes (or just buying school supplies for around 286,000 children?)

## In Conclusion

inBloom really never had a chance. Straddled with a top-heavy governance and leadership team that seemed unwilling or unable to involve a critical mass of lower-level individuals (both as project contributors and advisors), they produced a product that no one was really asking for that violated certain open standards in what may have been a bid to insitute vendor lock-in on a massive market of educational providers. Due to anemic audibility on organizational and project goals, there were few defenders and available applications for the product at launch, and little opportunity for contributors to work on core components of the data warehouse. These failures of adherence to best practices of open source development and open source benefits lead to revolts by end-users and stakeholders, a lack of applications, and concerns over data privacy and security. Resolution of these issues by increasing transparency, openness, and audibility to concerns at all stakeholder levels - from individual educators to parents and more - would be critical to align the governance and community standards to the best practices of open source development. Finally, enabling greater access to source code and involving the developer community at earlier developmental stages of the underlying API, data schema, and project plan would have lead to greater availability of applications and would have dovetailed with more open governance and possibly quelled fears of improper data usage.

_Austin Parker_
_10/1/2014_

[1]: http://en.wikipedia.org/wiki/InBloom "Wikipedia: inBloom"
[2]: http://blogs.edweek.org/edweek/DigitalEducation/2014/04/inbloom_to_shut_down_amid_growing_data_privacy_concerns.html "edWeek: inBloom to Shut Down Amid Growing Data-Privacy Concerns"
[3]: http://www.huffingtonpost.com/2013/06/12/nsa-big-data_n_3423482.html "Huffington Post: NSA Spying Controversy Highlights Embrace Of Big Data"
[4]: http://www.theatlantic.com/technology/archive/2014/07/data-science-what-the-facebook-controversy-is-really-about/373770/ "The Atlantic: What The Facebook Controversy Is Really About"
[5]: http://www.cbsnews.com/news/has-okcupid-played-with-users-hearts/ "CBS News: Has OKCupid Played With Users Hearts?"
[6]: https://github.com/inbloom "GitHub: inBloom"
[7]: rsc/inbloom_githeader.png "screenshot of inbloom github repo"
[8]: rsc/inBloomCETIS.pdf "PDF: inBloom to implement Learning Registry and LRMI"
[9]: rsc/AbelBlogPost.pdf "PDF: IMS Global Blog Post"
[10]: http://en.wikipedia.org/wiki/Eric_S._Raymond "Wikipedia: ESR"
[11]: rsc/Benefits_Guidelines.pdf "PDF: OSD Guidelines and Open Source Benefits"
[12]: rsc/inBloom_Products_Services.pdf "PDF: inBloom Products"
[13]: http://www.joelonsoftware.com/articles/fog0000000054.html "Joel Spolsky: Chicken and Egg Problems"
[14]: rsc/inbloom_dev_jumpstart.pdf "PDF: Developer Jumpstart Slide Deck"
[15]: rsc/inBloomAbout.pdf "PDF: About inBloom"
[16]: http://www.christenseninstitute.org "Christensen Institute Home Page"
[17]: http://en.wikipedia.org/wiki/The_Innovator's_Dilemma "Wikipedia: The Innovator's Dilemma"
[18]: http://www.newyorker.com/magazine/2014/06/23/the-disruption-machine "New Yorker: The Disruption Machine"
[19]: http://en.wikipedia.org/wiki/Soylent_(drink) "Wikipedia: Soylent"
[20]: http://www.getwashio.com "washio Home Page"
[21]: https://www.google.com/trends/explore#q=uber%20scandal&cmpt=q "Google Trends for 'uber scandal'"
[22]: http://www.uber.com "Uber Home Page"
[23]: http://www.nydailynews.com/news/crime/uber-driver-kidnaps-woman-article-1.1816459 "NY Daily News: Uber driver kidnapped woman, planned to sexually assault her: cops"
[24]: http://washboard.co "Washboard Home Page"
[25]: rsc/inBloomWaters.pdf "hackeducation.com: More Details on InBloom's Plans for Student Data"
[26]: http://www.ascd.org/publications/educational-leadership/feb05/vol62/num05/-The-Funding-Gap.aspx "ASCD: The Funding Gap Feb. 2005"
[27]: http://www.washingtonpost.com/blogs/answer-sheet/wp/2012/11/25/how-grossly-underfunded-are-public-schools/ "Washington Post: How grossly underfunded are public schools?"
[28]: http://www.nbcnews.com/business/economy/back-school-costs-soar-burdening-poor-n175546 "NBC News: Back-to-School Costs Soar, Burdening the Poor"
[29]: http://en.wikipedia.org/wiki/College_tuition_in_the_United_States#Overview_of_tuition_rates_in_the_U.S. "Wikipedia: College tuition in the United States"