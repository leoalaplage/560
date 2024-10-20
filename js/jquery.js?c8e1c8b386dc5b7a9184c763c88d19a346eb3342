var lwi = -1;
function thresholdPassed() {
    var w = document.documentElement.clientWidth;
    var p = false;
    var cw = 0;
    if (w >= 1200) {
        cw++;
    }
    if (lwi != cw) {
        p = true;
    }
    lwi = cw;
    return p;
}
var ready = function() {
    !function() {
        var e = document.querySelectorAll('a[href^="#"]');
        [].forEach.call(e, function(e) {
            var t = navigator.userAgent
              , a = /chrome/i.test(t)
              , o = /firefox/i.test(t)
              , n = /iPad|iPhone|iPod/.test(t) && !window.MSStream || "MacIntel" === navigator.platform && navigator.maxTouchPoints > 1;
            e.addEventListener("click", function(t) {
                var r = !1
                  , i = document.body.parentNode;
                n && "none" != getComputedStyle(i).getPropertyValue("scroll-snap-type") && (i.setAttribute("data-snap", i.style.scrollSnapType),
                i.style.scrollSnapType = "none",
                r = !0);
                var s = 0;
                if (e.hash.length > 1) {
                    var u = parseFloat(getComputedStyle(document.body).getPropertyValue("zoom"));
                    !o && u || (u = 1);
                    var l = e.hash.slice(1)
                      , c = document.getElementById(l);
                    if (null === c && null === (c = document.querySelector('[name="' + l + '"]')))
                        return;
                    s = a ? c.getBoundingClientRect().top * u + pageYOffset : (c.getBoundingClientRect().top + pageYOffset) * u
                } else if (r)
                    for (var m = document.querySelectorAll("[data-block-group]"), p = 0; p < m.length; p++)
                        if ("none" != getComputedStyle(m[p]).getPropertyValue("scroll-snap-align")) {
                            c = m[p];
                            break
                        }
                if (r)
                    window.smoothScroll(t, c, 1);
                else if ("scrollBehavior"in document.documentElement.style)
                    scroll({
                        top: s,
                        left: 0,
                        behavior: "smooth"
                    });
                else if ("requestAnimationFrame"in window) {
                    var d = pageYOffset
                      , f = null;
                    requestAnimationFrame(function e(t) {
                        f || (f = t);
                        var a = (t - f) / 400;
                        scrollTo(0, d < s ? (s - d) * a + d : d - (d - s) * a),
                        a < 1 ? requestAnimationFrame(e) : scrollTo(0, s)
                    })
                } else
                    scrollTo(0, s);
                t.preventDefault()
            }, !1)
        })
    }(),
    window.smoothScroll = function(e, t, a, o) {
        e.stopImmediatePropagation();
        var n, r = pageYOffset;
        t ? (("string" == typeof t || t instanceof String) && (t = document.querySelector(t)),
        n = t.getBoundingClientRect().top) : n = -r;
        var i = navigator.userAgent
          , s = /chrome/i.test(i)
          , u = /firefox/i.test(i)
          , l = parseFloat(getComputedStyle(document.body).getPropertyValue("zoom"));
        !u && l || (l = 1);
        var c = n * l + (s ? 0 : r * (l - 1))
          , m = null;
        function p() {
            d(window.performance.now ? window.performance.now() : Date.now())
        }
        function d(e) {
            null === m && (m = e);
            var n = (e - m) / 1e3
              , i = function(e, t, a) {
                switch (o) {
                case "linear":
                    break;
                case "easeInQuad":
                    e *= e;
                    break;
                case "easeOutQuad":
                    e = 1 - (1 - e) * (1 - e);
                    break;
                case "easeInCubic":
                    e *= e * e;
                    break;
                case "easeOutCubic":
                    e = 1 - Math.pow(1 - e, 3);
                    break;
                case "easeInOutCubic":
                    e = e < .5 ? 4 * e * e * e : 1 - Math.pow(-2 * e + 2, 3) / 2;
                    break;
                case "easeInQuart":
                    e *= e * e * e;
                    break;
                case "easeOutQuart":
                    e = 1 - Math.pow(1 - e, 4);
                    break;
                case "easeInOutQuart":
                    e = e < .5 ? 8 * e * e * e * e : 1 - Math.pow(-2 * e + 2, 4) / 2;
                    break;
                case "easeInQuint":
                    e *= e * e * e * e;
                    break;
                case "easeOutQuint":
                    e = 1 - Math.pow(1 - e, 5);
                    break;
                case "easeInOutQuint":
                    e = e < .5 ? 16 * e * e * e * e * e : 1 - Math.pow(-2 * e + 2, 5) / 2;
                    break;
                case "easeInCirc":
                    e = 1 - Math.sqrt(1 - Math.pow(e, 2));
                    break;
                case "easeOutCirc":
                    e = Math.sqrt(1 - Math.pow(0, 2));
                    break;
                case "easeInOutCirc":
                    e = e < .5 ? (1 - Math.sqrt(1 - Math.pow(2 * e, 2))) / 2 : (Math.sqrt(1 - Math.pow(-2 * e + 2, 2)) + 1) / 2;
                    break;
                case "easeInOutQuad":
                default:
                    e = e < .5 ? 2 * e * e : 1 - Math.pow(-2 * e + 2, 2) / 2
                }
                e > 1 && (e = 1);
                return t + a * e
            }(n / a, r, c);
            window.scrollTo(0, i),
            n < a ? "requestAnimationFrame"in window ? requestAnimationFrame(d) : setTimeout(p, 1e3 / 120) : (/iPad|iPhone|iPod/.test(navigator.userAgent) && !window.MSStream || "MacIntel" === navigator.platform && navigator.maxTouchPoints > 1) && (t && t.scrollIntoView(),
            setTimeout(function() {
                var e = document.body.parentNode;
                e.style.scrollSnapType = e.getAttribute("data-snap"),
                e.removeAttribute("data-snap")
            }, 100))
        }
        return "requestAnimationFrame"in window ? requestAnimationFrame(d) : setTimeout(p, 1e3 / 120),
        !1
    }
    ;
    !function() {
        var e = null;
        if (location.hash) {
            var t = location.hash.replace("#", "")
              , n = function() {
                var o = document.getElementById(t);
                null === o && (o = document.querySelector('[name="' + t + '"]')),
                o && o.scrollIntoView(!0),
                "0px" === window.getComputedStyle(document.body).getPropertyValue("min-width") ? setTimeout(n, 100) : null != e && setTimeout(e, 100)
            };
            n()
        } else
            null != e && e()
    }();
};
load = function() {}
;
"interactive" == document.readyState ? (ready(),
window.addEventListener("load", load)) : "complete" == document.readyState ? (ready(),
load()) : document.addEventListener("readystatechange", function() {
    "interactive" == document.readyState && ready(),
    "complete" == document.readyState && load()
});
