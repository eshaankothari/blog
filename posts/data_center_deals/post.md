---
title: The Money Behind the AI Data Center Boom
dek: "I pulled all the data center 8-Ks from the SEC for the past 5 years so you don't have to. Here are the largest players and how the deals were structured"
byline: Eshaan Kothari
date: 2026-08-26
layout: story
data:
  deals: data/deals.csv
  sponsors: data/sponsors.csv
  offtakers: data/offtakers.csv
  lenders: data/lenders.csv
  arrangers: data/arrangers.csv
  deal_types: data/deal_types.csv
  debt_by_year: data/debt_by_year.csv
  coupons: data/coupons.csv
  treasury: data/treasury_10y.csv
  largest_debt: data/largest_debt_deals.csv
  by_state: data/by_state.csv
  countries: data/countries.csv
source: SEC EDGAR full-text search (efts.sec.gov), 8-K filings 2021–2026; Infra Deal Project extraction
---


There is billions of dollars going into building out data centers to support the exponential demand in compute that crypto-mining and AI inference has caused. Using the EDGAR API, I pulled all the filed 8-Ks regarding data center buildout from the past 5 years (2021 to 2026) to analyze the scale and structuring of these data center deals. Building an agent to extrapolate key information from these long legal documents, this post presents findings from 281 distinct deals involving some of the largest companies in the world.

## Overview of data center buildout

```exhibit figures
items:
- {value: 281, label: distinct deals}
- {value: 442, label: $bn disclosed}
- {value: 86483, label: MW disclosed}
- {value: 42.2, label: $bn debt raised, dec: 1}
source: SEC EDGAR 8-K filings
```

```exhibit bubble_map
{title: Megawatts by state, data: by_state, state: state, size: mw, shade: deals, source: SEC EDGAR 8-K filings}
```

```exhibit ranked_bars
{title: Deals outside the US, data: countries, label: country, value: deals, top: 10, source: SEC EDGAR 8-K filings}
```

We can see that most of the recent buildout is happening in Texas for a variety of reasons. They have incentivized buildout under tax exemptions like House Bill 1223—where qualifying projects investing at least $200 million are exempt from state sales taxes on servers, cooling equipment, electrical gear, and electricity itself. They also have their own ISO in ERCOT, which makes speed to power less of a hassle, and they have relatively cheaper electricity costs ([EIA, average retail price of electricity by state](https://www.eia.gov/electricity/monthly/epm_table_grapher.php?t=epmt_5_6_a)).

Countries like India, Spain, and Canada have seen a lot of buildout as well, barring that these deals involve US-filing companies.

## How much money is there going into data centers over the past few years?

```exhibit bars
{title: Dollars by year and deal type ($mm), data: deals, x: year, y: usd_mm, series: type_group, mode: stacked, source: SEC EDGAR 8-K filings; 2026 to 19 August}
```

There are billions of dollars every year, and there has been a steady growth each year in the amount of money going into data centers. This is a clear response to the demand for AI-related compute.

## Who are the largest players?

These deals are complicated and involve a lot of different players that are typical for project and corporate finance deals (which infrastructure deals essentially boil down to). These include: sponsors, lenders, offtakers, and arrangers. I have mapped the most active players in each role.

Data centers cost a lot of money to build, and sponsors who want to make them do not want to take on all the capital expenditure or debt on their books (for a variety of reasons, including making future debt deals more expensive). Therefore, they have financing partners who are infrastructure funds and banks that help finance these data centers, often through debt, while the investors keep a small equity position.

Arrangers help make these complicated financial transactions go through, and offtakers are the companies that actually will use the data centers. This is where the topic of circular economy comes into play since we have been seeing the largest tech/AI companies be both the sponsors and the offtakers (i.e., the people who build, operate, and use the data center).

### Sponsors

```exhibit ranked_bars
title: Sponsors, by deals
data: sponsors
label: party
value: deals
top: 10
highlight: [Applied Digital, Core Scientific]
tip: '{party}: {deals} deals · ${usd_mm_full_credit:,.0f}mm · {mw:,.0f} MW'
span: 6
source: SEC EDGAR 8-K filings
```

```exhibit ranked_bars
title: Sponsors, by dollars ($mm)
data: sponsors
label: party
value: usd_mm_full_credit
top: 10
highlight: [Applied Digital, Core Scientific]
tone: c1
tip: '{party}: {deals} deals · ${usd_mm_full_credit:,.0f}mm · {mw:,.0f} MW'
span: 6
source: SEC EDGAR 8-K filings
```

### Offtakers

```exhibit ranked_bars
title: Offtakers, by deals
data: offtakers
label: party
value: deals
top: 10
highlight: [CoreWeave, Fluidstack]
tip: '{party}: {deals} deals · ${usd_mm_full_credit:,.0f}mm · {mw:,.0f} MW'
span: 6
source: SEC EDGAR 8-K filings
```

```exhibit ranked_bars
title: Offtakers, by dollars ($mm)
data: offtakers
label: party
value: usd_mm_full_credit
top: 10
highlight: [CoreWeave, Fluidstack]
tone: c1
tip: '{party}: {deals} deals · ${usd_mm_full_credit:,.0f}mm · {mw:,.0f} MW'
span: 6
source: SEC EDGAR 8-K filings
```

### Lenders

```exhibit ranked_bars
title: Lenders, by deals
data: lenders
label: party
value: deals
top: 10
highlight: [Macquarie]
tip: '{party}: {deals} deals · ${usd_mm_full_credit:,.0f}mm'
span: 6
source: SEC EDGAR 8-K filings
```

```exhibit ranked_bars
title: Lenders, by dollars ($mm)
data: lenders
label: party
value: usd_mm_full_credit
top: 10
highlight: [Macquarie]
tone: c1
tip: '{party}: {deals} deals · ${usd_mm_full_credit:,.0f}mm'
span: 6
source: SEC EDGAR 8-K filings
```

### Arrangers

```exhibit ranked_bars
title: Arrangers, by deals
data: arrangers
label: party
value: deals
top: 10
highlight: [Morgan Stanley, JPMorgan, Goldman Sachs]
tip: '{party}: {deals} deals · ${usd_mm_full_credit:,.0f}mm'
span: 6
source: SEC EDGAR 8-K filings
```

```exhibit ranked_bars
title: Arrangers, by dollars ($mm)
data: arrangers
label: party
value: usd_mm_full_credit
top: 10
highlight: [Morgan Stanley, JPMorgan, Goldman Sachs]
tone: c1
tip: '{party}: {deals} deals · ${usd_mm_full_credit:,.0f}mm'
span: 6
source: SEC EDGAR 8-K filings
```

The names that keep coming up are Applied Digital and Core Scientific on the sponsor side - both former bitcoin miners that turned their power-heavy sites into GPU data centers leased almost entirely to CoreWeave, which is by far the biggest offtaker with 25 deals. On the money side, Macquarie is the one lender that shows up over and over, and Morgan Stanley, JPMorgan, and Goldman are arranging most of the big notes.

```exhibit quadrants
title: Most active in each role
panels:
- {title: Sponsors, data: sponsors, label: party, value: deals, top: 5}
- {title: Offtakers, data: offtakers, label: party, value: deals, top: 5}
- {title: Lenders, data: lenders, label: party, value: deals, top: 5}
- {title: Arrangers, data: arrangers, label: party, value: deals, top: 5}
source: SEC EDGAR 8-K filings
```

## What types of deals are these?

```exhibit ranked_bars
title: Deals by type
data: deal_types
label: short
value: deals
top: 8
highlight: [Lease, Debt financing]
tip: '{deal_type}: {deals} deals · ${usd_mm:,.0f}mm'
span: 6
source: SEC EDGAR 8-K filings
```

```exhibit ranked_bars
title: Dollars by type ($mm)
data: deal_types
label: short
value: usd_mm
top: 8
highlight: [Lease, Debt financing]
tone: c1
tip: '{deal_type}: ${usd_mm:,.0f}mm · {deals} deals'
span: 6
source: SEC EDGAR 8-K filings
```

We can see that a majority of these deals are lease agreements. With other infrastructure assets like energy plants, developers make money by selling the output (energy in MW) of the asset, usually in long-term energy contracts with utilities called PPAs. The data center equivalent of that is entering a lease agreement with the people who will use the data center servers (i.e., offtakers).

We also see many acquisitions. That is either sponsors taking more equity stake in their data centers (e.g., Digital Realty buying Blackstone shares in Virginia data centers), or wealthy banks and sponsors buying smaller companies to vertically integrate more of the data center buildout process, whether that is development, maintenance, or the inference itself.

We can also see that debt is the bread-and-butter of financing data centers, whether through senior-secured notes or private credit lines (see next section for more). There is some equity financing on the sponsor side, with them owning a stake in the data center (e.g., Digital Realty).

## How much debt is needed to finance these data centers?

```exhibit table
title: The largest debt facilities
data: largest_debt
columns: [date, filer, usd_mm, mw, headline]
numeric: [usd_mm, mw]
links: {headline: url}
top: 10
source: SEC EDGAR 8-K filings
```

Lenders are financing data centers via debt vehicles at interest rates higher than other long-term bonds.

```exhibit line
{title: 10-year US Treasury yield (%), data: treasury, x: month, y: yield_pct, fmt: '{:.1f}%', source: 'FRED, 10-Year Treasury Constant Maturity Rate (DGS10); monthly averages'}
```

```exhibit lollipop
{title: Coupons on senior secured data center notes (%), data: coupons, label: note, value: coupon_pct, dec: 3, source: SEC EDGAR 8-K filings; fixed-coupon notes only}
```

We can see from a fund's perspective these are pretty safe deals that offer better returns than other bonds and offer the advantage of being senior-secured with the physical asset put up as collateral.

However, the bet I am willing to make from analyzing these deals is that sponsors, particularly smaller ones, are looking for more sources of debt financing—many do not partner with large firms, unlike some of the large data center deals with big tech companies, and sell their senior-secured notes to a variety of investors. Tokenization allows everyday investors to be those investors. Expanding the capital base with which these sponsors raise their debt financing without them having to deal with the hassle and operational costs of catering to retail investors could be an enticing opportunity for them, which is what tokenization allows for. Sponsors may even want to raise more money with the asset live for O&M costs. While it seems that infrastructure funds have no lack of interest in investing in data centers, expanding their capital base with which they raise the billions of dollars could be another use case for tokenization.

Of course, the only true way to test if these are real problems is by asking the sponsors and lenders themselves, which is a next step.

## Next steps

- Analyze past debt deals to see how many lenders are involved, what instruments, and how banks build the financial risk models to come up with debt structure for these deals
- Understand what the energy mix is, interconnection issues, and partners for all these data centers and more - this can help us understand on a deeper level the data center supply chain and which companies are involved at each level.
- Energy and data centers are inextricably linked—and a similar analysis can be applied to more infrastructure assets, including energy.
- Examine the profitability of data centers and data center companies to build a live pricing model for these assets based on their outputs.

## References

```exhibit table
title: All 281 deals
data: deals
columns: [date, filer, deal_type, usd_mm, mw, headline]
numeric: [usd_mm, mw]
links: {headline: url}
collapsed: Show all 281 deals
source: SEC EDGAR 8-K filings
note: A row is a deal, not a filing; each headline links to the SEC document
```
