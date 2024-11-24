---
title: Hardware Security
---
## Important Ideas

Perfect security does not exist.

Security is not a binary property (secure vs. not secure).

A *secure* system is one that has well-defined [[cia triad|security properties]] enforced by specific mechanisms against well-defined [[threat model|threat models]].

There can be flaws in the properties, mechanisms, and threat models.

The adversary can either be [[active attacker|active]] or [[passive attacker|passive]].

In computer systems, there is usually a notion of [[protection rings]].

**Channel**. A pathway or medium through which information can be transferred.

**Leakage channel**. A channel through which sensitive/confidential information inadvertently leaks from a system.

**Trojan**. A malicious component (software or hardware) that appears to be legitimate/harmless, but secretly carries out unauthorized/harmful activities.

Leakage channels are categorized in one of two ways:
* **Side channel.** A channel that leaks information through observable side effects of a system's operation.
* **Covert channel**. A channel created by an attacker to leak information.
	* Usually via a Trojan or exploiting the system in a way not intended by its designers.

They are also categorized in another one of two ways:
* **Storage channel**. A channel that gathers information via a functional component of the system.
* **Timing channel**. A channel that gathers information via timing of events in a system.