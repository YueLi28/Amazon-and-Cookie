#Related Paper

__I Do Not Know What You Visited Last Summer: Protecting Users from Third-party Web Tracking with TrackingFree Browser (NDSS 2015)__
This paper tries to address third party tracking mechanism by isolation by assigning web content to different principles. Each principle has its own persistant storage, which stores __Cookies__ or __EverCookies__. (To my understanding, each principle is like an incognito window) 

On top of the isolation concept, the authors created a first-of-its-kind browser -- TrackingFree. TrackingFree adressed challenges such as content allocation, principle communication (explict like postMessage in HTML5 and implicit like history sharing). 

* Initial content allocation is based on the registered domain name. TrackingFree groups webpages from the same site into one principal.
* Plugin objects such as Flash or SilverLight are treated like other HTML objects. Therefore they are put into the same principle as their embedding frames.
* TrackingFree keeps all non-user-triggered child frames in the principals that their parent frames reside in, and all user-triggered cross-site frames to other principals.
* Principal switch depends on whether target principal is user triggered (Keep in the same principal if not user triggerd, a different principle if user triggered.)
* To select principal is also important. TrackingFree keeps each principal being at most switched to 3 times to preserve privacy. 


__Selling Off Privacy at Auction (NDSS 2014)__
This paper studies Real-Time Bidding (RTB) and Cookie Matching (CM) in online advertisement ecosystem. RTB is like an auction that ad publishers sell ad spaces to bidders. Ad exchanger serves as the host and broadcast its own cookie and some context information to bidders. Bidders analyze the user and context to raise a price. Highest price wins the bid. The authors recruit volunteer to use their firefox plugins to browser the network normally. Then they gather data from these volunteers to detect and analyze RTB and CM.

Besides, the paper also talks about privacy leakage in cookie matching and braodcasting. When being broadcasted, the bidders will receive cookie and ccontext information (E.g the referrer URL), thus they can passively learn the user browsing history. If a cookie matching occured, the bidders can even link the user browsing history of their own as well as the ad exchanger. 