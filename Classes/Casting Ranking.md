# Casting Ranking
Aside from [[Practitioner Ranking]] in terms of how many [[Thema|Themas]] they have mastered, there is also something to be considered to how many times and how fast they can execute their Lu command starting from initialization of the Lor to overwriting Zaak. As it would be expected, a [[Septette]] can generally cast their spells faster and more frequently than a [[Trinity]] and same goes for [[Trinity]] in comparison to [[Practitioner|Practitioners]]. However, even so, there are differences between in the same [[Practitioner Ranking]], and as such, a more precise measurement method was needed to gauge oneself and their opponent.

As such multiple important variables were determined for Lu commands to devise a Casting Rank for each individual:
	1) Spell Cooldown - how long one needs to wait until a recast;
	2) [[Lethality Ranking|Lethality]];
	3) [[Area of Effect (AOE) Ranking|AOE]];
	4) Duration - how long the spell lasts;
	5) Maximum Cast Count - how many times the practitioner can cast it;
	6) Casting Time - how long it takes for the caster to cast it.

From those variables we can construct a simple equation to account for exponential growth and the compounding effect which arises from each of the variables.

_Let: c be Spell Cooldown in seconds, [[Lethality Ranking|L]] be [[Lethality Ranking|Lethality]] (A = 3, B = 2, C = 1, D = 0), [[Area of Effect (AOE) Ranking|A]] be [[Area of Effect (AOE) Ranking|AOE]] (Catastrophic = 6, Tactical = 5 ... None = 0), d be Duration in seconds, m be the Maximum Cast Count, t be Casting Time, s be an infinitely small value approaching 0._

_Using these predefined variables, R<sub>s</sub> be the Casting Ranking value for a single spell:_
$$R_{s}=\ln\left( \frac{1}{c+s} \right)+\ln\left( \frac{1}{t+s} \right)+\ln(m+s)+\ln(d+s)+e^L+e^A$$
_Which can be further simplified down as follows:_
$$R_{s}=\ln\left( \frac{1}{ct+s} \right))+\ln(m+s)+\ln(d+s)+\ln(e^{e^L}+s)+\ln(e^{e^A}+s)$$
$$R_{s}=\ln(1)-\ln(ct+s)+\ln(m+s)+\ln(m+s)+\ln(d+s)+\ln(e^{e^L}+s)+\ln(e^{e^A}+s)$$
$$R_{s}=\ln(mde^{e^L+e^A}+s)-\ln(ct+s)$$
_Or, alternatively, one could construct a sum function as follows where set S contains: {m, d, e<sup>e<sup>L</sup></sup>, e<sup>e<sup>A</sup></sup>}:_
$$R_{s}=\sum^{| S |}_{i=1}[\ln(S_{i}+s)]-\ln(ct+s)$$
_Having formulated a sum function from R<sub>s</sub> it is possible to further express the entirety of a practitioner's Lu command arsenal._

_Let there be a set I such that iot contains every Lu command a practitioner has, such that each element of I is a set of {S={m, d, e<sup>e<sup>L</sup></sup>, e<sup>e<sup>A</sup></sup>}, c, t} for each Lu command/spell._

_Let function f = R<sub>s</sub>, R be such that R<sub>n</sub> = f(I<sub>n</sub>), function g be such that g(R<sub>n</sub>) = S<sub>m</sub>, R<sub>c</sub> be a value calculated from set R such that each iterated value is weighted against its own maximum cast count._
$$R_{c}=\sum^{| R |}_{i=1}\left( 1-\frac{1}{g(R_{i})+1+s} \right)\times R_{i}$$
_or_
$$R_{c}=\sum^{| I |}_{i=1}\left( \frac{{g(f(I_{i}))+s}}{g(f(I_{i}))+s+1} \right)\times f(I_{i})$$
_Which can be further simplified down to:_
$$R_{c}=\sum^{| R |}_{i=1}\frac{{g(R_{i})\times R_{i}}}{g(R_{i})+1}$$
_or_
$$R_{c}=\sum^{| I |}_{i=1}=\frac{{g(f(I_{i}))\times f(I_{i})}}{g(f(I_{i}))+1}$$
