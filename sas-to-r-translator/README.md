SAS → R Translator
A browser-based tool that uses Claude (Anthropic's AI) to translate legacy SAS code into modern, idiomatic R. Built as a practical supplement to support Statistics Canada's Centre for Housing and Income Statistics (CHIS) modernization initiative, which is transitioning the Canadian Housing Survey from SAS to R.
Why I Built This
The CHIS team is actively migrating legacy SAS processes to R. This tool automates the first step of that workflow: understanding what a SAS script does and producing an equivalent R translation with clear notes on the decisions made. It's designed to help analysts who are comfortable in SAS get up to speed in R faster, and to reduce the friction of translating large volumes of legacy code.
What It Does

Paste any SAS code into the left panel and get translated R code on the right
Explains what the original SAS code does in plain English
Provides translation notes covering key differences, gotchas, and which R packages were used
Prefers tidyverse conventions in output (dplyr, ggplot2, tidyr) to match modern R best practices
Includes five built-in examples covering common SAS procedures relevant to survey data work: PROC MEANS, PROC SORT, DATA STEP, PROC REG, and macros

Tech Stack

Vanilla HTML, CSS, JavaScript (zero dependencies, runs in any browser)
Anthropic Claude API (claude-sonnet) for translation and explanation
R syntax highlighting rendered client-side

How to Run

Clone the repo
Open index.html in any modern browser (no server or build step needed)
Enter your Anthropic API key in the top right corner
Paste SAS code and click Translate, or use Ctrl+Enter

You can get an Anthropic API key at https://console.anthropic.com. New accounts include free credits.
Limitations

Translation quality depends on the complexity of the SAS code. Standard procedures (PROC MEANS, PROC FREQ, PROC REG, DATA steps) translate reliably. Complex macros or organization-specific SAS libraries may need manual review.
The tool does not have access to your actual datasets, so translated code should be tested before use in production pipelines.
API key is entered client-side and never stored or transmitted anywhere except directly to Anthropic's API.

Relevance to Housing Data Work
The built-in examples use variable names and procedures consistent with housing survey workflows (household income, monthly rent, province-level breakdowns, regression modeling). The tool is intentionally scoped to the kinds of SAS patterns that appear most frequently in survey data processing and statistical reporting pipelines.

Built by Manav Sharma