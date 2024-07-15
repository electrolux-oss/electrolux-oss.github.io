# Reimagining Cloud Cost Management: A Product-Centric Approach at Electrolux

Have you ever gotten that sinking feeling when you see your cloud bill? It’s natural for costs to rise alongside a growing business, but is it inevitable?
In this article, we’ll delve into our Platform Engineering team’s experience at Electrolux. We’ll explore how we transformed cloud cost management, moving from a manual, team-dependent process to a product-centric approach. This approach empowers individual teams to understand and optimize their spending, and ultimately led to the creation of an open-source product we’re excited to share.


## The Challenge of Cloud Cost Management

Regardless of how many cloud vendors you use, controlling costs can be a challenge. We faced this while migrating our primary connectivity system to AWS. Each month, I compiled a report for management, gathering data from a labyrinth of consoles — Azure Portal, AWS Cost Explorer, GCP dashboard… the list goes on. This process often took several days, with some data delayed by finance since we shared costs.

During this period, our team also transitioned from an infrastructure operations focus to a Platform Engineering approach, focusing on developer experience. So when I voiced frustration over the tedious manual process, my team suggested that automation was not only possible but necessary.

## From Manual to Automated: The Evolution Begins

Our initial automated solution was simple but generated significant interest across our org. For the first time, cloud costs were aggregated and accessible through a UI, sparking a growing appetite for understanding cloud expenditures.
What if more users joined? How does scalability affect costs? How much do we spend per product, service, or namespace? What does it cost to connect a single fridge or oven? Where can we reduce costs? Adding 2 million devices should not necessitate five more developers or increase connection costs proportionally.

Next releases included calculators and drop-downs for resources, services, and namespaces. We excelled in tagging resources, promoting tags within our internal infrastructure management tool (see more on InfraKitchen). Our daily-used observability platform now incorporated cloud costs, thanks to cost exporters integrated with Prometheus. These [exporters](https://github.com/electrolux-oss), accepted by Prometheus — the leading open-source observability solution — scrape information from cloud vendors and convert it into metrics (here is [the link on Prometheus FinOps section](https://prometheus.io/docs/instrumenting/exporters/#finops)).

Our solution grew complex and difficult to maintain, prompting us to explore the market for replacements. Each tool we evaluated had similar limitations, often lacking vendor support without significant wait times. We didn’t sign any contracts, as our in-house solution met all our needs and was free.

## Educating for Long-Term Success: The Cost Optimization Program

Centralized cost control by our infra team worked well initially, but we recognized the potential in enabling each team to monitor their own costs. We had one-hour monthly sessions to identify spikes and suggest optimizations. However, teams, knowing their products, architecture, and business cases best, created new infrastructure as our organization grew. Manual tracking became unsustainable.

Despite having the best tools tailored to our needs, we realized that building these features internally didn’t translate to a widespread understanding of FinOps concepts. To address this, we launched a cost optimization program — a 3-month initiative designed to educate product teams on cloud costs, key drivers, and cost-saving actions. Due to the holiday season, we extended the program to January.

The goal was to raise cost awareness rather than merely save money. Over 10 teams joined, and five excelled. We collaborated closely with AWS, who provided deep dives into pricing models, best practices, and specific use case advice. AWS also facilitated a FinOps workshop, introducing tools and methodologies.

Monthly reviews with AWS highlighted optimization opportunities, and our SRE team held monthly check-ins with product teams to address questions. This initiative led to product teams analyzing costs from various perspectives — some focusing on databases, others on logs/metrics, and some optimizing CI/CD pipelines.

Key insights gained from this program include understanding vendors’ complex pricing models, essential for decision-making. For instance, data transfer costs vary by region. However, the most significant outcome was the 20% reduction in our monthly cloud costs achieved through this simple initiative.

After presenting our journey at conferences like AWS Summit, Datadog Summit, Code Europe, and others, we received overwhelming interest from engineers who wanted to use our internal solution. This positive response led us to open-source the tool, making it available to the broader engineering community.

## Open-Sourcing InfraWallet

After these two years of dedicated effort and expertise, we open-sourced our internal solution as [InfraWallet](https://prometheus.io/docs/instrumenting/exporters/#finops), our comprehensive cloud cost management solution. By open-sourcing this tool, we hope to empower other organizations to achieve similar success in cloud cost management, fostering a collaborative community dedicated to financial efficiency and transparency.

For more information and to join the InfraWallet community, visit [our GitHub repository](https://github.com/electrolux-oss/infrawallet) and start your journey towards optimized cloud cost management today.
