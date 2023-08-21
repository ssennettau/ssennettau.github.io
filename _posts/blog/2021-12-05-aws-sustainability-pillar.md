---
title: Sustainability on AWS (re:Invent 2021)
author: ssennett
heroimage: /assets/images/posts/a3086c02-aad7-4dcf-9112-92454232ca67.png
date: 2021-12-05 00:00:00 +1000
category: blog
---

Werner Vogels is an unparalleled titan of cloud computing, and his Keynote is one of the most popular sessions of re:Invent. And when he [announced the new Sustainability Pillar](https://aws.amazon.com/blogs/aws/sustainability-pillar-well-architected-framework/) of the AWS Well-Architected Framework at re:Invent this week, it was met with plenty of excitement.

If you haven't read the paper on the new [Sustainability Pillar](https://docs.aws.amazon.com/wellarchitected/latest/sustainability-pillar/sustainability-pillar.html) or seen Werner's keynote yet (starting 1:28:19), I'd encourage you to check them out.

## Amazon's Role in Sustainability

Amazon's original pledge to use 100% renewable energy has been revised. With an original target of 2030, they now predict to be fully sustainable by 2025; **just three years away** (I know, it still feels like mid-2020 to me too), with a global capacity of 12GW.

![The Shared Responsibility Model for Sustainability](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1v06be1hzbgutk3zhv2l.png)

One of the underlying concepts they've introduced is their Shared Responsibility Model. The breakdown is brilliantly succinct, just as it is for security:

* AWS is responsible for the sustainability **of** the cloud
* You are responsible for the sustainability **in** the cloud

But really... can we please not name it the same as the other [AWS Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/), or at least unify them both?

## Measurability

Measuring your organization's climate impact is extremely challenging, let alone when your technology is running on mysterious black boxes in locations half-way around the world that you'll never see.

> "Moving on-premise workloads to AWS can lower your carbon footprint by 88%"  -- Dr. Werner Vogels

While AWS's economies of scale definitely mean byte-for-byte, your workload will be less carbon impactful than a traditional datacenter, it's not enough if you don't know how your footprint is looking.

As far as measuring your footprint in AWS goes at the moment, you can basically say "less resources, less carbon", and that your bill is a great proxy metric for that. If you're spending money on resources, it's consuming electricity, after all.

![AWS Customer Carbon Footprint Tool announcement](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/4553lo6bny6iovbzgi5z.png)

AWS announcing the pending release of the **AWS Customer Carbon Footprint Tool** is some *really* exciting news. It's also one of the rare cases where AWS have announced something that isn't yet publicly available, which says something.

Along with your current usage, it will also project your carbon footprint into the future, including accounting for AWS's growing use of renewable energy.

The day we can quantify our environmental impact in the cloud is the day we can use it as a metric to meaningfully drive our impact down.

## Practical steps

Okay, so this is all cool; but how can you actually drive down that impact? In a phrase: "Use the least possible".

> "The greenest energy is the energy you don't use"  -- Peter DeSantis

The Sustainability Pillar includes a section on [Best practices for sustainability in the cloud](https://docs.aws.amazon.com/wellarchitected/latest/sustainability-pillar/best-practices-for-sustainability-in-the-cloud.html), which is written better than I ever could, and I won't repeat it all.

One thing that Peter DeSantis did cover in his [re:Invent 2021 Keynote](https://www.youtube.com/watch?v=9NEQbFLtDmg) (also highly recommended, brilliant presenter) was how AWS's use of specialized hardware also opens new opportunities.

![Presentation highlighting the AWS Graviton, Inferentia, and Trainium processors](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/7s741gmuelvre8dekudd.png)

In Machine Learning, Trainium and Inferentia (those names tho...) are highly optimized for their specific tasks, and that includes their power efficiency. And for general compute, Graviton (now with Graviton3!) offers similar advantages not just in price, but resource efficiency also.

Another big one is Lambda. With AWS controlling the resourcing allocation to execute each of these individual functions, plus abstracting away so much of the underlying infrastructure, it's an incredibly efficient way not just to build and run code, but also to make the best use of the resources underneath it; including electricity.

There's a full session on ARC325 Architecting for sustainability (currently only on the re:Invent site) available as well, if you want to dive deeper

## Relationship to the other pillars

![The now-six pillars of the Well-Architected Framework](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/cwosweab8kofq2k0nhsj.png)

Like all of the pillars, Sustainability is definitely mutually supporting of the other five pillars: [Operational Excellence](https://docs.aws.amazon.com/wellarchitected/latest/operational-excellence-pillar/welcome.html), [Security](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html), [Reliability](https://docs.aws.amazon.com/wellarchitected/latest/reliability-pillar/welcome.html), [Performance Efficiency](https://docs.aws.amazon.com/wellarchitected/latest/performance-efficiency-pillar/welcome.html), and [Cost Optimization](https://docs.aws.amazon.com/wellarchitected/latest/cost-optimization-pillar/welcome.html). But it adds some nuance in interesting ways.

Some points may feel counter-intuitive, such as [Back up data only when difficult to recreate](https://docs.aws.amazon.com/wellarchitected/latest/sustainability-pillar/back-up-data-only-when-its-difficult-to-recreate-it.html). The question is really whether there is *value* in backing up the data. Old crash dumps? Probably not. Core customer data? Definitely.

It suggests that the two scenarios as either where there is business value, or required for compliance purposes. But there may also be cases where even if data can be recreated that it would simply be more efficient to store it anyway. Complex video renders or machine learning models come to mind as two examples.

[Optimize impact on customer devices and equipment](https://docs.aws.amazon.com/wellarchitected/latest/sustainability-pillar/optimize-impact-on-customer-devices-and-equipment.html) flies in the face of some modern practices about pushing work to the edge and the front-end. But for any work of computational intensity, the efficiency is in the cloud.

Another point is that by reducing impact on customer devices, ensuring a light load, and optimizing for backwards compatibility, you ensure that the devices themselves are less prone to replacement. Along with reducing e-waste, it also just makes sense economically.

## What's next?

![Whitepaper documentation on Sustainability as a non-functional technical requirement](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/8uq6a3sq7bx5aasg81u2.png)

Companies, including yours and mine, need to get serious about measuring and reducing our impact on the climate. With the Carbon Footprint Tool on the way, I'm very excited to see how that may enlighten us all.

But our business and technology strategies must align too. Just as we mandate tooling and frameworks for consistent experience, so too must be consider how we define and action sustainability targets. With that in mind, here's a thought exercise:

> **How would you reduce your companies cloud carbon footprint by 25%?**

It's not so outlandish that those strategies will be ours to implement sooner than we think.