# TLS 1.3: List of Security Properties

This is a running list of security properties applicable to TLS 1.3. At this stage, this list is intended to be a place for contributors to add properties covered by their analyses and to provide links to the relevant resources. This list is also intended to capture properties that are desirable for TLS 1.3 (even if not currently covered by an analysis). 

This list will be consolidated periodically. 

## Secrecy Properties

Property | Informal Description | Expanded Description | Model Type | Formal Definition
------------ | ------------ | ------------------------- | ------------ | ------------ 
Property name | One or two sentences providing an intuitive description of the property | One or two paragraphs providing additional detail (still intended to be high-level/semi-formal) | Computational, symbolic | A [link](https://guides.github.com/features/mastering-markdown/) to the relevant paper/resource (feel free to add description files to the LaTex folder if required)
Session key secrecy | If an authenticated session key is established and the adversary has not revealed the long-term keys of the communicating peers, then the adversary does not know the session key. | This notion is one of syntactic secrecy, meaning that the adversary cannot obtain the shared session key. In the unilaterally authenticated case, only the client establishes an authenticated application data session key. The client is assured that if it establishes a session with an authenticated server, then the adversary does not know the application data session key. In the mutually authenticated case, both server and client establish an authenticated application data session key. Our modelling of this property implies perfect forward secrecy in the presence of an active adversary. We note that our model currently does not allow for the adversarial compromise of semi-static secrets (PSKs and semi-static server DH exponents). This adversary capability would affect the secrecy of the static secret in some cases. | Symbolic | [paper](http://tls13tamarin.github.io/TLS13Tamarin/docs/tls13tamarin.pdf)
Early data key secrecy | If an early data key is established (for use by the client) and the adversary has not revealed the long-term key of the server, then the adversary does not know the early data key. | This notion is one of syntactic secrecy, meaning that the adversary cannot obtain the early data key. We note that our model currently does not allow for the adversarial compromise of the semi-static server DH exponent. This adversary capability would affect the secrecy of the static secret, and hence of the early data key. | Symbolic | [paper](http://tls13tamarin.github.io/TLS13Tamarin/docs/tls13tamarin.pdf)

## Authentication Properties 

Property | Informal Description | Expanded Description | Model Type | Formal Definition
------------ | ------------ | ------------------------- | ------------ | ------------ 
Property name | One or two sentences providing an intuitive description of the property | One or two paragraphs providing more detail (still intended to be high-level/semi-formal)  | Computational, symbolic | A [link](https://guides.github.com/features/mastering-markdown/) to the relevant paper/resource (feel free to add description files to the LaTex folder if required)
Agreement | A session p agrees with p' on x when p.x = p'.x. For agreement on a set X we require that p agrees with p' on all x in X.| TLS provides authentication with agreement on X if sessions that authenticate their peer agree with it on all variables in X | both (Computationally this is expressed using negation and a negligible adversary advantage) | [Paper1](http://eprint.iacr.org/2016/072.pdf) for a multi-mode definition and [Paper2](http://tls13tamarin.github.io/TLS13Tamarin/docs/tls13tamarin.pdf) for a symbolic definition. 
Version downgrade protection | A client and server supporting TLS 1.3 should negotiate 1.3, even if they both support older versions of TLS | Let two TLS sessions be partnered when they have the same pair of nonces. TLS is version downgrade secure if partnered sessions always negotiate the version they would negotiate when no adversary is present. | both (Computationally this is expressed using negation and a negligible adversary advantage) | [Paper](http://eprint.iacr.org/2016/072.pdf) on downgrade definitions. 

## Other

Property | Informal Description | Expanded Description | Model Type | Formal Definition
------------ | ------------ | ------------------------- | ------------ | ------------ 
Property name | One or two sentences providing an intuitive description of the property | One or two paragraphs providing more detail (still intended to be high-level/semi-formal) | Computational, symbolic | A [link](https://guides.github.com/features/mastering-markdown/) to the relevant paper/resource (feel free  to add description files to the LaTex folder if required)