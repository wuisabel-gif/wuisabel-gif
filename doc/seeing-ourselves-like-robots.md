# Seeing Ourselves Like Robots

This summer I spent much of my time building the localization stack for an autonomous underwater vehicle.

On paper, the task sounds almost trivial. Before a robot can plan a path, avoid an obstacle, or complete a mission, it must answer a deceptively simple question:

Where am I?

I thought localization was a problem about position.

I was wrong.

It is really a problem about trust.

An underwater robot has no single source of truth. Its camera sees one version of the world. Its inertial measurement unit measures acceleration and rotation. A Doppler Velocity Log estimates velocity relative to the seafloor. A pressure sensor measures depth. Every sensor observes reality from a different perspective. Every one carries noise. Every one drifts. Every one eventually disagrees with another.

The estimator I spent the summer building—a GTSAM factor graph running incremental smoothing with iSAM2—exists for one purpose: to decide how much each of those imperfect observations deserves to be believed.

Every sensor enters the graph as a factor.

The IMU becomes a CombinedImuFactor, carrying motion through preintegration between keyframes. The camera contributes BetweenFactorPose3 constraints from ICP. The DVL constrains body-frame velocity. The depth sensor anchors vertical motion. None of them determines the answer by itself. Instead, every measurement enters with a covariance—a mathematical expression of uncertainty. In the optimization, no sensor is trusted absolutely. Every factor is allowed to pull on the estimate only as strongly as its uncertainty permits.

That idea stayed with me.

The first instinct, both in robotics and in life, is to ask which observation is correct.

Experience teaches a different lesson.

The real question is almost never Which sensor is lying?

It is Why do they disagree?

One afternoon our estimator insisted the vehicle had traveled hundreds of kilometers while it sat motionless on a workbench.

The IMU looked healthy.

The camera measurements looked reasonable.

The optimization converged.

Nothing appeared obviously broken.

Eventually we found the problem. The graph's very first pose, X(0), had been initialized with the wrong attitude. The vehicle rested at a slight tilt, but the estimator assumed it was perfectly level. Gravity, resolved in the wrong coordinate frame, became horizontal acceleration. The IMU faithfully measured that acceleration. Preintegration faithfully accumulated it. Every subsequent factor built upon that mistaken beginning.

The measurements were not wrong.

The interpretation was.

That discovery changed how I thought about localization.

For a long time, I assumed the most important sensor was the camera. Humans tend to believe the same thing. "I saw it with my own eyes," we say, as though vision settles every argument.

But underwater robotics quickly teaches otherwise.

Water clouds. Light scatters. Cameras fail.

The vehicle keeps navigating anyway.

It falls back on inertial measurements, velocity estimates, pressure, and whatever reliable information remains. Vision was never the foundation of localization. It was only one factor among many.

People seem remarkably similar.

What we believe about ourselves is not built from vision alone. We assemble an understanding of who we are from memory, experience, conversations, successes, failures, habits, and the quiet influence of people around us. Every one of those sources is incomplete. Every one carries uncertainty. None deserves absolute confidence.

Perhaps we, too, are continuously performing sensor fusion.

The summer offered another lesson.

After fixing the initialization bug, we discovered something subtler. A valid IMU attitude alone was still not enough to begin localization. Before the estimator was allowed to create its first state, it had to wait for another source of information—a DVL measurement, a depth reading, or another observation tying the robot to the outside world.

The engineering lesson was simple.

A good attitude was necessary, but not sufficient.

That phrase lingered in my mind.

Many things in life feel exactly like that.

Confidence is necessary, but not sufficient.

Talent is necessary, but not sufficient.

Conviction is necessary, but not sufficient.

An estimator built entirely on one sensor becomes unstable. A person who relies on only one perspective often does too.

Working on Barracuda also changed how I think about disagreement.

Late in the summer we encountered a curious problem. Two sensors disagreed about something as fundamental as which way was down. One reported the vehicle upright. The other insisted it was almost perfectly inverted.

Neither sensor was malfunctioning.

The mistake lived between them.

An old software correction had been applied in the wrong coordinate frame, silently flipping the relationship between imu_link and base_link. Both sensors were honestly reporting what they believed to be true. They simply inhabited different frames of reference.

That realization felt strangely familiar.

When people disagree, we often assume one of them must be wrong.

Robotics suggests another possibility.

Perhaps they are describing the world from different coordinate frames.

Perhaps the disagreement lies not in the observations themselves, but in the assumptions connecting them.

In robotics, residuals are valuable precisely because they reveal those hidden assumptions. When two factors disagree, the optimizer is forced to ask whether the underlying model is still correct.

People might benefit from doing the same.

Perhaps wisdom is not the confidence to trust one observation completely.

Perhaps it is the willingness to assign every belief an honest covariance—to recognize uncertainty, to let independent evidence constrain our conclusions, and to revise our estimate when new information arrives.

The longer I worked on localization, the less it felt like an engineering problem.

It became a way of thinking.

A robot never truly knows where it is.

It maintains only the best estimate it can, given imperfect information.

Perhaps people do the same.

We do not discover ourselves once and for all.

We spend our lives updating the estimate.
