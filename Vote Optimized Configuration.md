- `mostly_confirmed_threshold` 
		Recommended Value by default is 0.38. Lowering this value lead to increasing instability and voting on non-valid forks. Raising it could slow down the voting, thus leading to a delay of several slots and loss of credits. Deviating from the 0.38 value is generally not advisable. A small increase in this value may be justified if the validator knows for sure that there is a problem with voting on invalid forks.
- `threshold_ahead_count` 
		Recommended Range: 1 to 3 slots. This range is chosen to be proactive in pursuing vote credits but not overly aggressive. Can help maximize Timely Vote Credits by allowing the validator to be slightly earlier in voting on forks that are rapidly gaining confirmation.
		**Avoid very high values (e.g., > 4-5):** Setting this parameter too high significantly increases the risk of the validator rapidly reaching the `VOTE_THRESHOLD_DEPTH` limit, especially if the chosen fork does not quickly gain supermajority support. This can lead to the validator entering a `FailedThreshold` state, where it temporarily stops voting, thereby accumulating missed votes.
- `after_skip_threshold` 
		Recommended Value: 1. This option offers the best balance for most scenarios. This acts as a filter against weak forks while allowing for a quicker voting compared to waiting for full supermajority. 
		0 - too risky. Period of missed slots creates uncertainty in the network. Voting for the first block that comes along will often result in voting on an invalid fork.
		2 - too conservative. Waiting for a supermajority to confirm results in long pauses during which the validator does not vote and loses credits.
- `threshold_escape_count` 
		Recommended Range: 16 to 32 slots. Most likely 24 is the most suitable option. There is nothing to change. 