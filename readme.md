# h①②③ – Accessibility HTML5 Outliner

v1.2

See the headings like a screenreader!

## Add to your bookmarks

[Show Headings][1]
[Test Link][2]

[h①②③][1]
[H1️⃣2️⃣3️⃣][1]
[h❶❷❸][1]

## Why you should

If you are a web developer, you might have heard of sectioning content. Those were introduced with article, nav, section and such to provide a scope for headings and footers. They allowed to semantically structure an HTML document.

    <h1>I am a document</h1>
    <section>
      <h1>I am a section</h1>
      <p>A great section really!</p>
      <aside>
        <h1>Some advertising in between</h1>
        <a href="https://www.chocoloco.com">
          <img
            src="advertising-animated.gif"
            alt="Some fancy sweet chocolate drink"
            >
        </a>
      </aside>
      <p>Still belong to the section</p>
    </section>
    <section>
      <h1>Another section</h1>
      <p>And more content for the people</p>
    </section>

The main reason web developers embraced this change was a very practical one: it solved an annoying issue with the heading hierarchy. You'd always had to number the headings h1, h2 etc. imagine a teaser component. Now let's place this teaser into the body, but also into an accordeon. The heading now has to change depending on its place, because the accordion is some levels deeper. This is a nightmare for modular system. So that's why devs loved those h1 in sections.

But reality turned out to be different. While devs embraced the news, browsers and screenreaders (and most probably SEOs) did not: they sticked to the yet existing model. A document full of h1 (well structured within sectioning elements) is total rubbish for a blind user, denying him or her the most important navigational help. The above example has this structure:

1. I am a document
2. I am a section
3. Some advertising in between
4. Another section

The new HTML 5.2 spec takes a step back and now recommends to always set your h1, h2, h3 etc. according the actual level. For accessibility reasons though, you should rely on implicit sectioning at all: forget about sections and you're all set with screenreaders (and probably search engines too).

    <h1>I am a document</h1>
    <section>
      <h2>I am a section</h2>
      <p>A great section really!</p>
      <aside>
        <h2>Some advertising in between</h2>
        <a href="https://www.chocoloco.com">
          <img
            src="advertising-animated.gif"
            alt="Some fancy sweet chocolate drink"
            >
        </a>
      </aside>
      <h2>I am a section (continue)</h2>
      <p>Still belong to the section</p>
    </section>
    <section>
      <h2>Another section</hh21>
      <p>And more content for the people</p>
    </section>

Thing is that many people don't know. Some outliners show the structure of the whole document, including hidden parts. But guess what, screenreaders only read what's visible. Yeah, funny thing, right. If you think about it, it makes just sense though. So this outliner will only consider headings that are actually visible, at least visible to the screenreader. (because you can visually hide elements that stay theoretically visible).

Our bookmarklet to the rescue!! :-)

[2]: https://test.com
[1]: javascript:(function(){%22use%20strict%22%3Bfunction%20_createForOfIteratorHelper(e%2Ct)%7Bvar%20i%3D%22undefined%22!%3Dtypeof%20Symbol%26%26e%5BSymbol.iterator%5D%7C%7Ce%5B%22%40%40iterator%22%5D%3Bif(!i)%7Bif(Array.isArray(e)%7C%7C(i%3D_unsupportedIterableToArray(e))%7C%7Ct%26%26e%26%26%22number%22%3D%3Dtypeof%20e.length)%7Bi%26%26(e%3Di)%3Bvar%20o%3D0%2Cn%3Dfunction()%7B%7D%3Breturn%7Bs%3An%2Cn%3Afunction()%7Breturn%20o%3E%3De.length%3F%7Bdone%3A!0%7D%3A%7Bdone%3A!1%2Cvalue%3Ae%5Bo%2B%2B%5D%7D%7D%2Ce%3Afunction(e)%7Bthrow%20e%7D%2Cf%3An%7D%7Dthrow%20new%20TypeError(%22Invalid%20attempt%20to%20iterate%20non-iterable%20instance.%5CnIn%20order%20to%20be%20iterable%2C%20non-array%20objects%20must%20have%20a%20%5BSymbol.iterator%5D()%20method.%22)%7Dvar%20r%2Cl%3D!0%2Ca%3D!1%3Breturn%7Bs%3Afunction()%7Bi%3Di.call(e)%7D%2Cn%3Afunction()%7Bvar%20e%3Di.next()%3Breturn%20l%3De.done%2Ce%7D%2Ce%3Afunction(e)%7Ba%3D!0%2Cr%3De%7D%2Cf%3Afunction()%7Btry%7Bl%7C%7Cnull%3D%3Di.return%7C%7Ci.return()%7Dfinally%7Bif(a)throw%20r%7D%7D%7D%7Dfunction%20_toConsumableArray(e)%7Breturn%20_arrayWithoutHoles(e)%7C%7C_iterableToArray(e)%7C%7C_unsupportedIterableToArray(e)%7C%7C_nonIterableSpread()%7Dfunction%20_nonIterableSpread()%7Bthrow%20new%20TypeError(%22Invalid%20attempt%20to%20spread%20non-iterable%20instance.%5CnIn%20order%20to%20be%20iterable%2C%20non-array%20objects%20must%20have%20a%20%5BSymbol.iterator%5D()%20method.%22)%7Dfunction%20_unsupportedIterableToArray(e%2Ct)%7Bif(e)%7Bif(%22string%22%3D%3Dtypeof%20e)return%20_arrayLikeToArray(e%2Ct)%3Bvar%20i%3D%7B%7D.toString.call(e).slice(8%2C-1)%3Breturn%22Object%22%3D%3D%3Di%26%26e.constructor%26%26(i%3De.constructor.name)%2C%22Map%22%3D%3D%3Di%7C%7C%22Set%22%3D%3D%3Di%3FArray.from(e)%3A%22Arguments%22%3D%3D%3Di%7C%7C%2F%5E(%3F%3AUi%7CI)nt(%3F%3A8%7C16%7C32)(%3F%3AClamped)%3FArray%24%2F.test(i)%3F_arrayLikeToArray(e%2Ct)%3Avoid%200%7D%7Dfunction%20_iterableToArray(e)%7Bif(%22undefined%22!%3Dtypeof%20Symbol%26%26null!%3De%5BSymbol.iterator%5D%7C%7Cnull!%3De%5B%22%40%40iterator%22%5D)return%20Array.from(e)%7Dfunction%20_arrayWithoutHoles(e)%7Bif(Array.isArray(e))return%20_arrayLikeToArray(e)%7Dfunction%20_arrayLikeToArray(e%2Ct)%7B(null%3D%3Dt%7C%7Ct%3Ee.length)%26%26(t%3De.length)%3Bfor(var%20i%3D0%2Co%3DArray(t)%3Bi%3Ct%3Bi%2B%2B)o%5Bi%5D%3De%5Bi%5D%3Breturn%20o%7Dvar%20containerId%3D%22a11y-bookmarklet%22%2CcontainerStyle%3D%22position%3A%20fixed%3B%20top%3A%200%3B%20right%3A%200%3B%20max-height%3A%20100%25%3B%20box-shadow%3A%200%200%2080px%20rgba(0%2C0%2C0%2C0.3)%3B%20width%3A%2020%25%3B%20min-width%3A%20320px%3B%20max-width%3A%20450px%3B%20z-index%3A%201000001%3B%22%2ChighlighterEl%3Ddocument.createElement(%22DIV%22)%3BhighlighterEl.id%3D%22h1-a11y-highlighterelement%22%2ChighlighterEl.style.cssText%3D%22pointer-events%3A%20none%3B%20position%3A%20fixed%3B%20border%3A%201px%20dashed%20%230081BE%3B%20box-shadow%3A%200%200%2054px%200%20rgba(0%2C84%2C150%2C0.3)%3B%20display%3A%20none%3B%20z-index%3A%201000000%3B%20transition%3A%20all%20200ms%3B%22%3Bvar%20container%3Ddocument.getElementById(containerId)%3Bcontainer%26%26document.body.removeChild(container)%2C(container%3Ddocument.createElement(%22DIV%22)).id%3DcontainerId%2Ccontainer.style.cssText%3DcontainerStyle%3Bvar%20iframe%3Ddocument.createElement(%22IFRAME%22)%3Biframe.style.width%3D%22100%25%22%2Ciframe.style.height%3D%22100%25%22%2Ciframe.style.borderWidth%3D%220%22%2Ciframe.setAttribute(%22title%22%2C%22H123%22)%3Bvar%20doc%2Coutline%3DgetOutline()%3Bfunction%20updateHeight()%7Bcontainer.style.height%3D%220px%22%2Ccontainer.style.height%3Ddoc.scrollingElement.scrollHeight%2B%22px%22%7Dfunction%20getOutline()%7Bfor(var%20e%3D0%2Ct%3DcustomQuerySelectorAll(document%2C'%3Ais(h1%2Ch2%2Ch3%2Ch4%2Ch5%2Ch6%2Ch7%2C%5Brole%3D%22heading%22%5D)%3Anot(%5Brole%3D%22presentation%22%5D)')%2Ci%3D%5B%5D%2Co%3D0%3Bo%3Ct.length%3Bo%2B%2B)%7Bvar%20n%3Dt%5Bo%5D%2Cr%3DisVisible(t%5Bo%5D)%2Cl%3DparseInt(n.getAttribute(%22aria-level%22)%7C%7Cn.nodeName.charAt(1))%3Bif(r)%7Bvar%20a%3Dl%3Ee%26%26l!%3D%3De%2B1%3Be%3Dl%7Delse%20a%3D!1%3Bi.push(%7Bvisible%3Ar%2Cvisuallyhidden%3Ar%26%26isVisuallyHidden(n)%2Cwrong%3Aa%2Clevel%3Al%2Cel%3An%7D)%7Dreturn%20i%7Dfunction%20countOutline(e%2Ct)%7Bfor(var%20i%3D0%2Co%3D0%3Bo%3Ce.length%3Bo%2B%2B)e%5Bo%5D%5Bt%5D%26%26i%2B%2B%3Breturn%20i%7Dfunction%20outlineToHTML(e)%7Bfor(var%20t%3D%22%22%2Ci%3D0%3Bi%3Ce.length%3Bi%2B%2B)%7Bvar%20o%3De%5Bi%5D%2Cn%3DtextContent(o.el).trim()%3Bt%2B%3D'%3Cli%20class%3D%22'%2Ct%2B%3Do.wrong%3F%22wrong-level%22%3A%22correct-level%22%2Ct%2B%3Do.visible%3F%22%22%3A%22%20hidden%22%2Ct%2B%3Do.visuallyhidden%3F%22%20visuallyhidden%22%3A%22%22%2Ct%2B%3Dn%3F%22%22%3A%22%20empty%22%2Ct%2B%3D'%22%20style%3D%22margin-left%3A%20'%2Bo.level%2B'em%3B%22%3E'%2Ct%2B%3D'%3Ca%20href%3D%22%23'%2Bi%2B'%22%20target%3D%22_top%22%3E'%2Ct%2B%3D'%3Cspan%20class%3D%22level%22%20data-level%3D%22'%2Bo.level%2B'%22%3E%3C%2Fspan%3E%20'%2Ct%2B%3D'%3Cspan%20class%3D%22text%22%3E'%2B(n%3FhtmlEntities(n)%3A%22%5Bempty%20or%20non-text%20heading%5D%22)%2B%22%3C%2Fspan%3E%22%2Ct%2B%3D%22%3C%2Fa%3E%22%2Ct%2B%3D%22%3C%2Fli%3E%22%7Dreturn'%3Cul%20id%3D%22headings%22%3E'%2Bt%2B%22%3C%2Ful%3E%22%7Dfunction%20htmlEntities(e)%7Breturn%20String(e).replace(%2F%26%2Fg%2C%22%26amp%3B%22).replace(%2F%3C%2Fg%2C%22%26lt%3B%22).replace(%2F%3E%2Fg%2C%22%26gt%3B%22).replace(%2F%22%2Fg%2C%22%26quot%3B%22)%7Dfunction%20isVisible(e)%7Bfor(var%20t%3Dwindow.getComputedStyle(e)%2Ci%3D!1%3Be%3B)%7Bif(%22none%22%3D%3D%3Dt.display)return!1%3Bif(!i)%7Bif(%22hidden%22%3D%3D%3Dt.visibility)return!1%3B%22visible%22%3D%3D%3Dt.visibility%26%26(i%3D!0)%7Dif(%22true%22%3D%3D%3De.getAttribute(%22aria-hidden%22))return!1%3Bvar%20o%3De.assignedSlot%7C%7Ce%3Be%3Do.parentElement%7C%7Co.getRootNode().host%3Btry%7Bt%3Dwindow.getComputedStyle(e)%7Dcatch(e)%7Breturn!0%7D%7Dreturn!0%7Dfunction%20isVisuallyHidden(e)%7Bvar%20t%3De.getBoundingClientRect(e)%3Bif(%22absolute%22%3D%3D%3Dwindow.getComputedStyle(e).position)%7Bif(t.width%3C%3D1%26%26t.height%3C%3D1)return!0%3Bif(t.right%3C%3D0)return!0%7D%7Dfunction%20highlightElement(e%2Ct)%7Bt%7C%7C(e.scrollIntoViewIfNeeded%3Fe.scrollIntoViewIfNeeded()%3Ae.scrollIntoView%26%26e.scrollIntoView())%2CsetTimeout((function()%7Bfor(var%20t%3De.getBoundingClientRect()%2Ci%3De.parentElement%3B!t.height%26%26!t.width%26%26!t.left%26%26!t.top%26%26i%3B)t%3Di.getBoundingClientRect()%2Ci%3Di.parentElement%3Bi%26%26((t%3D%7Bleft%3At.left%2Ctop%3At.top%2Cbottom%3At.bottom%2Cright%3At.right%7D).left%3DMath.min(window.innerWidth%2Ct.left)%2Ct.right%3DMath.max(0%2Ct.right)%2Ct.top%3DMath.min(window.innerHeight%2Ct.top)%2Ct.bottom%3DMath.max(0%2Ct.bottom)%2Cdocument.getElementById(highlighterEl.id)%7C%7Cdocument.body.appendChild(highlighterEl)%2ChighlighterEl.style.left%3Dt.left-10%2B%22px%22%2ChighlighterEl.style.width%3Dt.right-t.left%2B20%2B%22px%22%2ChighlighterEl.style.top%3Dt.top-10%2B%22px%22%2ChighlighterEl.style.height%3Dt.bottom-t.top%2B20%2B%22px%22%2ChighlighterEl.style.display%3D%22block%22)%7D)%2C100)%7Dfunction%20handleHoverHighlight(e)%7Bvar%20t%3Dfunction()%7Be.checked%3FenableHoverHighlight()%3AdisableHoverHighlight()%7D%3Bt()%2Ce.addEventListener(%22click%22%2Ct)%7Dfunction%20highlightLink(e)%7Bfor(var%20t%3Ddoc.querySelectorAll(%22%23headings%20a%22)%2Ci%3Dt.length-1%3Bi%3E%3D0%3Bi--)t%5Bi%5D%3D%3D%3De%3Ft%5Bi%5D.classList.add(%22is-active%22)%3At%5Bi%5D.classList.remove(%22is-active%22)%7Dfunction%20handleElementHover(e)%7Bfor(var%20t%3De.target%2Ci%3Ddocument.body.querySelectorAll(%22*%22)%2Co%3D!1%2Cn%3Di.length-1%3Bn%3E%3D0%3Bn--)%7Bvar%20r%3Di%5Bn%5D%3Bif(o)%7Bfor(var%20l%3Doutline.length-1%3Bl%3E%3D0%3Bl--)if(outline%5Bl%5D.el%3D%3D%3Dr%26%26outline%5Bl%5D.visible)return%20highlightElement(outline%5Bl%5D.el%2C!0)%2Cvoid%20highlightLink(doc.querySelector('%23headings%20a%5Bhref%3D%22%23'%2Bl%2B'%22%5D'))%7Delse%20r%3D%3D%3Dt%26%26(o%3D!0%2Cn%2B%2B)%7DhighlightLink(null)%7Dfunction%20enableHoverHighlight()%7Bdocument.body.addEventListener(%22mouseover%22%2ChandleElementHover)%7Dfunction%20disableHoverHighlight()%7Bdocument.body.removeEventListener(%22mouseover%22%2ChandleElementHover)%7Dfunction%20customQuerySelectorAll(e%2Ct)%7Bfor(var%20i%2Co%3D%5B%5D%2Cn%3Ddocument.createNodeIterator(e%2CNode.ELEMENT_NODE)%3Bi%3Dn.nextNode()%3B)i.matches(t)%3Fo.push(i)%3Ai.shadowRoot%26%26o.push.apply(o%2C_toConsumableArray(customQuerySelectorAll(i.shadowRoot%2Ct)))%3Breturn%20o%7Dfunction%20textContent(e)%7Bvar%20t%2Ci%3D%5Be.textContent%5D%2Co%3D_createForOfIteratorHelper(e.querySelectorAll(%22slot%22))%3Btry%7Bfor(o.s()%3B!(t%3Do.n()).done%3B)%7Bvar%20n%2Cr%3D_createForOfIteratorHelper(t.value.assignedNodes())%3Btry%7Bfor(r.s()%3B!(n%3Dr.n()).done%3B)%7Bvar%20l%3Dn.value%3Bi.push(l.textContent)%7D%7Dcatch(e)%7Br.e(e)%7Dfinally%7Br.f()%7D%7D%7Dcatch(e)%7Bo.e(e)%7Dfinally%7Bo.f()%7Dreturn%20i.filter(Boolean).join(%22%20%22)%7Dcontainer.appendChild(iframe)%2Ciframe.onload%3Dfunction()%7Biframe.onload%3Dfunction()%7B%7D%2C(doc%3Diframe.contentWindow.document).open()%2Cdoc.write('%3Chtml%3E%20%3Chead%3E%20%3Cmeta%20name%3D%22viewport%22%20content%3D%22width%3Ddevice-width%2Cminimum-scale%3D1.0%2Cinitial-scale%3D1%2Cuser-scalable%3Dyes%22%3E%20%3Cstyle%3E%20*%20%7B%20margin%3A%200%3B%20padding%3A%200%3B%20border%3A%200%3B%20%7D%20body%20%7B%20font%3A%2014px%2F1.6%20sans%3B%20font-family%3A%20-apple-system%2C%20BlinkMacSystemFont%2C%20%22Segoe%20UI%22%2C%20Helvetica%2C%20Arial%2C%20sans-serif%2C%20%22Apple%20Color%20Emoji%22%2C%20%22Segoe%20UI%20Emoji%22%2C%20%22Segoe%20UI%20Symbol%22%3B%20color%3A%20%23284900%3B%20background%3A%20rgba(255%2C255%2C255%2C0.95)%3B%20white-space%3A%20nowrap%3B%20overflow-x%3A%20hidden%3B%20text-overflow%3A%20ellipsis%3B%20padding%3A%2015px%3B%20padding-bottom%3A%2030px%3B%20%7D%20ul%20%7B%20margin%3A%200%200%200%20-10px%3B%20padding%3A%200%3B%20%7D%20li%20%7B%20color%3A%20%23284900%3B%20list-style%3A%20none%3B%20margin-left%3A%2020px%3B%20display%3A%20-webkit-flex%3B%20display%3A%20flex%3B%20%7D%20a%20%7B%20color%3A%20inherit%3B%20text-decoration%3A%20none%3B%20display%3A%20inline-block%3B%20max-width%3A%2030em%3B%20overflow%3A%20hidden%3B%20text-overflow%3A%20ellipsis%3B%20padding%3A%202px%204px%202px%2025px%3B%20position%3A%20relative%3B%20line-height%3A%201.3%3B%20border-radius%3A%203px%3B%20%7D%20a%20%3E%20.level%20%7B%20display%3A%20inline-block%3B%20background-color%3A%20currentColor%3B%20font-size%3A%2085%25%3B%20font-weight%3A%20bold%3B%20width%3A%202.7ex%3B%20height%3A%202.7ex%3B%20text-align%3A%20center%3B%20box-sizing%3A%20border-box%3B%20position%3A%20absolute%3B%20left%3A%202px%3B%20top%3A%202px%3B%20padding-top%3A%201px%3B%20%7D%20a%20%3E%20.level%3Abefore%20%7B%20content%3A%20attr(data-level)%3B%20color%3A%20white%3B%20%7D%20li.hidden%20%7B%20color%3A%20black%3B%20text-decoration%3A%20line-through%3B%20opacity%3A%200.5%3B%20%7D%20li.empty%20%7B%20font-style%3A%20italic%3B%20%7D%20.result%3Anot(.show-hidden)%20li.hidden%20%7B%20display%3A%20none%3B%20%7D%20.result.mark-visuallyhidden%20li.visuallyhidden%20.level%3Abefore%20%7B%20color%3A%20inherit%3B%20%7D%20.result.mark-visuallyhidden%20li.visuallyhidden%20.level%20%7B%20border%3A%201px%20dashed%3B%20background%3A%20white%3B%20%7D%20li.wrong-level%20%7B%20color%3A%20%23AF3A37%3B%20%7D%20a.is-active%20%7B%20box-shadow%3A%200%200%205px%201px%20%233CBEFF%3B%20%7D%20a%3Ahover%20%7B%20background-color%3A%20currentColor%3B%20%7D%20a%3Ahover%20%3E%20.text%20%7B%20color%3A%20white%3B%20%7D%20a%3Ahover%20%3E%20.level%20%7B%20background-color%3A%20transparent%3B%20%7D%20header%20%7B%20padding-top%3A%205px%3B%20padding-bottom%3A%2015px%3B%20padding-right%3A%205em%3B%20margin-bottom%3A%201em%3B%20border-bottom%3A%201px%20solid%20%23eee%3B%20%7D%20legend%20%7B%20margin-right%3A%201em%3B%20font-weight%3A%20bold%3B%20%7D%20%40media%20(min-width%3A%20340px)%20%7B%20legend%20%7B%20float%3A%20left%3B%20%7D%20%7D%20.options%20%7B%20display%3A%20-webkit-flex%3B%20display%3A%20flex%3B%20-webkit-flex-wrap%3A%20wrap%3B%20flex-wrap%3A%20wrap%3B%20%7D%20.options%20.input%20%7B%20margin-right%3A%202em%3B%20%7D%20.count%20%7B%20background%3A%20%23ddd%3B%20border-radius%3A%204px%3B%20padding%3A%201px%203px%3B%20%7D%20.tooltip%20%7B%20position%3A%20relative%3B%20%7D%20.tooltip%3Abefore%20%7B%20content%3A%20%5C'%E2%84%B9%EF%B8%8F%5C'%3B%20%7D%20.tooltip%3Afocus%3Aafter%2C%20.tooltip%3Ahover%3Aafter%20%7B%20content%3A%20attr(title)%3B%20position%3A%20absolute%3B%20background%3A%20white%3B%20padding%3A%204px%2010px%3B%20top%3A%2070%25%3B%20left%3A%2070%25%3B%20width%3A%2010em%3B%20box-shadow%3A%200%202px%2020px%20rgba(0%2C0%2C0%2C0.3)%3B%20white-space%3A%20normal%3B%20border-radius%3A%208px%3B%20border-top-left-radius%3A%200%3B%20z-index%3A%201%3B%20pointer-events%3A%20none%3B%20%7D%20.button-close%20%7B%20position%3A%20absolute%3B%20top%3A%2015px%3B%20right%3A%2015px%3B%20padding%3A%205px%2010px%3B%20border-radius%3A%205px%3B%20border%3A%200%3B%20font-size%3A%20inherit%3B%20color%3A%20white%3B%20background-color%3A%20%23284900%3B%20cursor%3A%20pointer%3B%20%7D%20.button-close%3Ahover%20%7B%20color%3A%20white%3B%20background-color%3A%20%23284900%3B%20%7D%20%3C%2Fstyle%3E%20%3C%2Fhead%3E%20%3Cbody%3E%20%3Cheader%3E%20%3Cbutton%20class%3D%22button-close%22%20data-action%3D%22close%22%3EClose%3C%2Fbutton%3E%20%3Ch1%3EH123%3C%2Fh1%3E%20%3Cfieldset%3E%20%3Clegend%3EOptions%3C%2Flegend%3E%20%3Cdiv%20class%3D%22options%22%3E%20%3Cdiv%20class%3D%22input%22%3E%20%3Cinput%20type%3D%22checkbox%22%20name%3D%22options%22%20id%3D%22o-hidden%22%3E%20%3Clabel%20for%3D%22o-hidden%22%3EShow%20hidden%20%3Cspan%20class%3D%22count%22%20id%3D%22o-hidden-count%22%3E%3C%2Fspan%3E%20%3Cspan%20class%3D%22tooltip%22%20title%3D%22also%20hidden%20for%20screenreaders%22%20tabindex%3D%220%22%3E%3C%2Fspan%3E%3C%2Flabel%3E%20%3C%2Fdiv%3E%20%3Cdiv%20class%3D%22input%22%3E%20%3Cinput%20type%3D%22checkbox%22%20name%3D%22options%22%20id%3D%22o-visuallyhidden%22%3E%20%3Clabel%20for%3D%22o-visuallyhidden%22%3EMark%20visually%20hidden%20%3Cspan%20class%3D%22count%22%20id%3D%22o-visuallyhidden-count%22%3E%3C%2Fspan%3E%20%3Cspan%20class%3D%22tooltip%22%20title%3D%22only%20visible%20for%20screenreaders%22%20tabindex%3D%220%22%3E%3C%2Fspan%3E%3C%2Flabel%3E%20%3C%2Fdiv%3E%20%3Cdiv%20class%3D%22input%22%3E%20%3Cinput%20type%3D%22checkbox%22%20name%3D%22options%22%20id%3D%22o-highlight%22%3E%20%3Clabel%20for%3D%22o-highlight%22%3EHover-Highlight%20%3Cspan%20class%3D%22tooltip%22%20title%3D%22Highlight%20the%20corresponding%20heading%20when%20hovering%20over%20elements%20of%20the%20page%22%20tabindex%3D%220%22%3E%3C%2Fspan%3E%3C%2Flabel%3E%20%3C%2Fdiv%3E%20%3C%2Fdiv%3E%20%3C%2Ffieldset%3E%20%3C%2Fheader%3E%20%3Cmain%20id%3D%22result%22%20class%3D%22result%22%3E%20%3C%2Fmain%3E%20%3C%2Fbody%3E%20%3C%2Fhtml%3E%20')%2Cdoc.close()%3Bvar%20e%3Ddoc.querySelector('%5Bdata-action%3D%22close%22%5D')%3Be%26%26e.addEventListener(%22click%22%2C(function(e)%7BdisableHoverHighlight()%2Cwindow.removeEventListener(%22resize%22%2CupdateHeight)%2Cdocument.body.removeChild(container)%2Cdocument.getElementById(highlighterEl.id)%26%26document.body.removeChild(highlighterEl)%7D))%3Bvar%20t%3Ddoc.querySelector(%22%23result%22)%3Bfunction%20i(e%2Ct)%7Bvar%20i%3Ddoc.getElementById(e)%2Co%3Ddoc.querySelector(%22.result%22)%3Bif(i)%7Bvar%20n%3Dfunction(e)%7Bi.checked%3Fo.classList.add(t)%3Ao.classList.remove(t)%2Ce%26%26updateHeight()%7D%3Bi.addEventListener(%22change%22%2Cn%2C!1)%2Ci.addEventListener(%22click%22%2Cn%2C!1)%2Cn()%7D%7Dt%26%26(t.innerHTML%3DoutlineToHTML(outline))%2C(t%3Ddoc.querySelector(%22%23o-hidden-count%22))%26%26(t.innerText%3Doutline.length-countOutline(outline%2C%22visible%22))%2C(t%3Ddoc.querySelector(%22%23o-visuallyhidden-count%22))%26%26(t.innerText%3DcountOutline(outline%2C%22visuallyhidden%22))%2Ci(%22o-hidden%22%2C%22show-hidden%22)%2Ci(%22o-visuallyhidden%22%2C%22mark-visuallyhidden%22)%2ChandleHoverHighlight(doc.getElementById(%22o-highlight%22))%2CupdateHeight()%2Cdoc.addEventListener(%22mouseover%22%2C(function(e)%7Bvar%20t%3Bif(%22A%22%3D%3D%3De.target.nodeName.toUpperCase()%3Ft%3De.target%3Ae.target.parentElement%26%26%22A%22%3D%3D%3De.target.parentElement.nodeName.toUpperCase()%26%26(t%3De.target.parentElement)%2Ct)%7Bvar%20i%3DparseInt(t.getAttribute(%22href%22).substr(1)%2C10)%3BhighlightElement(outline%5Bi%5D.el)%7D%7D)%2C!1)%2Cwindow.addEventListener(%22resize%22%2CupdateHeight)%7D%2Cdocument.body.appendChild(container)%3B}())
