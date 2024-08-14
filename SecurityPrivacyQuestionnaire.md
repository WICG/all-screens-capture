## [2.1 What information might this feature expose to Web sites or other parties, and for what purposes is that exposure necessary?](https://www.w3.org/TR/security-privacy-questionnaire/#purpose)

This API enables allowlisted applications to capture the visible content shown on all screens of a client. Such a feature is needed in use cases where
regulation requires full documentation (e.g. in the financial sector, contact centers) or when a screen capture is needed for training purposes. See also the
use cases in the [Explainer](https://github.com/screen-share/capture-all-screens?tab=readme-ov-file#use-cases).

## [2.2 Do features in your specification expose the minimum amount of information necessary to enable their intended uses?](https://www.w3.org/TR/security-privacy-questionnaire/#minimum-data)

Yes. In case there is a legal requirement to capture all screens for compliance reasons, we cannot further restrict the screen capture.

## [2.3 How do the features in your specification deal with personal information, personally-identifiable information (PII), or information derived from them?](https://www.w3.org/TR/security-privacy-questionnaire/#personal-data)

We make sure that the administrator is making an intentional decision to allowlist the API for a narrow set of
[isolated web apps](https://github.com/WICG/isolated-web-apps). We further ensure that the user is warned in advance about a potential capture, as
well as when actual capturing is happening. Users have the chance to close any sensitive content or end the session before the screen is captured.

By exposing this API in [isolated web apps](https://github.com/WICG/isolated-web-apps) only, we minimize the risk of external parties having access
to the data through cross-site-scripting attacks.

## [2.4 How do the features in your specification deal with sensitive information?](https://www.w3.org/TR/security-privacy-questionnaire/#sensitive-data)

Access to the API is restricted to apps that are trusted by the administrator. Further, the API can be used only after the user is informed about
a potential future screen capture.
This way we ensure [meaningful constent](https://w3ctag.github.io/design-principles/#consent) by the administrator and the user,
and that the user can end the session before exposing sensitive information.

## [2.5 Do the features in your specification introduce new state for an origin that persists across browsing sessions?](https://www.w3.org/TR/security-privacy-questionnaire/#persistent-origin-specific-state)

No.

## [2.6 Do the features in your specification expose information about the underlying platform to origins?](https://www.w3.org/TR/security-privacy-questionnaire/#underlying-platform-data)

This API connects each captured screen to it's corresponding [ScreenDetailed](https://www.w3.org/TR/window-management/#api-screendetailed-interface) object.
Hence, the same access to platform specific data as described [here](https://www.w3.org/TR/window-management/#api-screendetailed-interface) applies.

## [2.7 Does this specification allow an origin to send data to the underlying platform?](https://www.w3.org/TR/security-privacy-questionnaire/#send-to-platform)

No.

## [2.8 Do features in this specification enable access to device sensors?](https://www.w3.org/TR/security-privacy-questionnaire/#sensor-data)

No.

## [2.9 Do features in this specification enable new script execution/loading mechanisms?](https://www.w3.org/TR/security-privacy-questionnaire/#string-to-script)

No.

## [2.10 Do features in this specification allow an origin to access other devices?](https://www.w3.org/TR/security-privacy-questionnaire/#remote-device)

No.

## [2.11 Do features in this specification allow an origin some measure of control over a user agent’s native UI?](https://www.w3.org/TR/security-privacy-questionnaire/#native-ui)

No.

## [2.12 What temporary identifiers do the features in this specification create or expose to the web?](https://www.w3.org/TR/security-privacy-questionnaire/#temporary-id)

No temporary identifiers (e.g. deviceIds) are exposed.

## [2.13 How does this specification distinguish between behavior in first-party and third-party contexts?](https://www.w3.org/TR/security-privacy-questionnaire/#first-third-party)

 By default, the "all-screens-capture" permissions policy prevents use from third-party contexts.
 In addition, [isolated web apps](https://github.com/WICG/isolated-web-apps) prevent third-party contexts from accessing this API.

## [2.14 How do the features in this specification work in the context of a browser’s Private Browsing or Incognito mode?](https://www.w3.org/TR/security-privacy-questionnaire/#private-browsing)

Not applicable. This API is intended to be used in [isolated web apps](https://github.com/WICG/isolated-web-apps) (which do not support either mode).

## [2.15 Does this specification have both "Security Considerations" and "Privacy Considerations" sections?](https://www.w3.org/TR/security-privacy-questionnaire/#considerations)

Yes.

## [2.16 Do features in your specification enable origins to downgrade default security protections?](https://www.w3.org/TR/security-privacy-questionnaire/#relaxed-sop)

Yes. This API does not require active user interaction for screen capture consent.

## [2.17 How does your feature handle non-"fully active" documents?](https://www.w3.org/TR/security-privacy-questionnaire/#non-fully-active)

Similarly to screen capture via [getDisplayMedia](https://www.w3.org/TR/screen-capture/#dom-mediadevices-getdisplaymedia),
the document will remain active while screen capture active.

## [2.18 What should this questionnaire have asked?](https://www.w3.org/TR/security-privacy-questionnaire/#missing-questions)

The questionnaire seems thorough.