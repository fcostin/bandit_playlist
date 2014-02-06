idea: bandit algorithm playlist generation
==========================================


goal
----

*	output an infinite sequence of track choices that is enjoyable to listen to, without wanting to change any settings
*	do this by learning, based on what the user does
*	dont think of this as a permutation of all songs. it is acceptable and desirable not to play horrible songs at all.


simplifying assumptions
-----------------------

*	letting an entire track play is a vote in favour. skipping to the next track is a vote against.
*	the pool of tracks is fixed, no new tracks are added
	-	could generalise later
*	ignore track rating metadata
*	initially treat all tracks as independent. ie no recommendation model to generalise between tracks
	-	could generalise later with contextual bandit approach
	-	per-albumn / per-artist features?
*	assume song preferences are invariant wrt mood/etc of listener
	-	could generalise later. probably need contextual bandit approach
	-	seed playback sequence with initial manual track choice(s)


implementation
--------------

*	try to infer a (relative?) desired playback frequency for each track
*	maintain playback history to measure frequency each track has been played
*	maintain votes for and against tracks (by listener actions / inactions)
*	use epsilon-greedy or UCB approach
*	use some kind of structured prediction approach? SEARN?? to generate sequences of tracks


platforms to consider deploying atop
------------------------------------

*	foobar2000 (windows, really nice, has SDK for plugins, C++)
	+	[example plugins](http://www.foobar2000.org/components)
	+	[SDK](http://www.foobar2000.org/SDK)
*	quodlibet (cross-platform, GTK, GPL, supports plugins, python)
	+	[example plugins](http://code.google.com/p/quodlibet/source/browse/plugins/README)
	+	[plugin api](http://code.google.com/p/quodlibet/source/browse/#hg%2Fquodlibet%2Fquodlibet%2Fplugins)


### maybe see also

*	[jwz: iTunes 11 still sucking](http://www.jwz.org/blog/2014/02/itunes-11-still-sucking/)


