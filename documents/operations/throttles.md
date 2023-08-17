Link: https://reserve.org/protocol/protocol_operations/#issuance-throttle
Title: Issuance & Redemption Throttles

Issuance throttle
As a way to limit the extractable value in the case of an attack or exploit of an RToken, the protocol allows the RToken deployer (and governance) to set a limit on how much RToken can be issued.

The throttling mechanism works as a battery, where, after a large isuance, the issuance limit recharges linearly to the defined maximum at a defined speed of recharge.

The idea is to ensure net issuance for an RToken never exceeds some bounds per unit time (hour). Limit can be set as a fixed amount of Rtokens (e.g. 1,000,000 rtokens) and/or as a percentage of the RToken supply (e.g. 5% as default).

Redemption throttle
Similar to the issuance throttle, each RToken can have a redemption throttle to limit the amount of extractable value in the case of an attack or exploit.

The throttling mechanism works as a battery, where, after a large redemption, the redemption limit recharges linearly to the defined maximum at a defined speed of recharge.

The idea is to ensure net redemption for an RToken never exceeds some bounds per unit time (hour). Limit can be set as a fixed amount of Rtokens (e.g. 1,000,000 rtokens) and/or as a percentage of the RToken supply (e.g. 2.5% as default).

Note: It is recommended that the redemption throttle is greater than the issuance throttle, to avoid to consume all the redemption throttle with an issue-redeem operation.
