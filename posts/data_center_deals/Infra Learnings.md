Title: Mapping all data center deals   
By: Eshaan Kothari

There is billions of dollars going into building out data centers to support the exponential demand in compute that crypto-mining and AI inference has caused. Using the EDGAR API, I pulled all the filed 8-Ks regarding data center buildout from the past 5 years (2021 to 2026\) to analyze the scale and structuring of these data center deals. Building an agent to extrapolate key information from these long legal documents, this post presents findings from over \_\_\_\_\_ distinct deals involving some of the largest companies in the world.

HEADING 2: Overview of data center buildout

INSERT: EXHIBIT 1  
CLAUDE: move up \- where the megawatts are and then outside the US graph

We can see that most of the recent buildout is happening in Texas for a variety of reasons. They have incentivized buildout under tax exemptions like House Bill 1223—where qualifying projects investing at least $200 million are exempt from state sales taxes on servers, cooling equipment, electrical gear, and electricity itself. They also have their own ISO in ERCOT, which makes speed to power less of a hassle, and they have relatively cheaper electricity costs (CLAUDE: include link to source for that EIA).

Countries like India, Spain, and Canada have seen a lot of buildout as well, barring that these deals involve US-filing companies.

HEADING 2: How much money is there going into data centers over the past few years?  
exhibit 3

There are billions of dollars every year, and there has been a steady growth each year in the amount of money going into data centers. This is a clear response to the demand for AI-related compute.

HEADING 2: Who are the largest players?

These deals are complicated and involve a lot of different players that are typical for project and corporate finance deals (which infrastructure deals essentially boil down to). These include: sponsors, lenders, offtakers, and arrangers. I have mapped the most active players in each role.

Data centers cost a lot of money to build, and sponsors who want to make them do not want to take on all the capital expenditure or debt on their books (for a variety of reasons, including making future debt deals more expensive). Therefore, they have financing partners who are infrastructure funds and banks that help finance these data centers, often through debt, while the investors keep a small equity position.

Arrangers help make these complicated financial transactions go through, and offtakers are the companies that actually will use the data centers. This is where the topic of circular economy comes into play since we have been seeing the largest tech/AI companies be both the sponsors and the offtakers (i.e., the people who build, operate, and use the data center).

Add existing graphs

CLAUDE: Write a short sentence about the biggest players and a bit about them in my style

CLAUDE: ADD A 4-QUADRANT MAP OF THE LARGEST PLAYERS IN EACH AT THE BOTTOM \- AND MAKE SOME VISUAL DISTINCTION BETWEEN THE GRAPHS

HEADING 2: What types of deals are these?

Graphs \- cleaner

We can see that a majority of these deals are lease agreements. With other infrastructure assets like energy plants, developers make money by selling the output (energy in MW) of the asset, usually in long-term energy contracts with utilities called PPAs. The data center equivalent of that is entering a lease agreement with the people who will use the data center servers (i.e., offtakers).

We also see many acquisitions. That is either sponsors taking more equity stake in their data centers (e.g., Digital Reality buying Blackstone shares in Virigina data centers), or wealthy banks and sponsors buying smaller companies to vertically integrate more of the data center buildout process, whether that is development, maintenance, or the inference itself.

We can also see that debt is the bread-and-butter of financing data centers, whether through senior-secured notes or private credit lines (see next section for more). There is some equity financing on the sponsor side, with them owning a stake in the data center (e.g., Digital Realty).

HEADING 2: How much debt is needed to finance these data centers?

Table with debt deals

Lenders are financing data centers via debt vehicles at interest rates higher than other long-term bonds.

CLAUDE: include a graph of 10-year treasury bond results  
CLAUDE: include the senior-secured note yield graph but maybe try something different than line graph 

We can see from a fund’s perspective these are pretty safe deals that offer better returns than other bonds and offer the advantage of being senior-secured with the physical asset put up as collateral. 

However, the bet I am willing to make from analyzing these deals is that sponsors, particularly smaller ones, are looking for more sources of debt financing—many do not partner with large firms, unlike some of the large data center deals with big tech companies. Expanding the capital base with which these sponsors raise their debt financing without them having to deal with the hassle and operational costs of catering to retail investors could be an enticing opportunity for them, which is what tokenization allows for. Sponsors may even want to raise more money with the asset live for O\&M costs. While it seems that infrastructure funds have no lack of interest in investing in data centers, expanding their capital base with which they raise the billions of dollars could be another use case for tokenization.

Of course, the only true way to test if these are real problems is by asking the sponsors and lenders themselves, which is a next step.

* HEADING 2: Next Steps  
  * Understand how banks build the financial risk models to come up with debt structure for these deals  
  * Understand what the energy mix is, interconnection issues, and partners for all these data centers and more \- this can help us understand on a deeper level the data center supply chain and which companies are involved at each level.  
  * Energy and data centers are inextricably linked—and a similar analysis can be applied to more infrastructure assets, including energy.  
  * Examine the profitability of data centers and data center companies to build a live pricing model for these assets based on their outputs.

REFERENCES  
CLAUDE: toggles to a drop down of all the deals for people to read 