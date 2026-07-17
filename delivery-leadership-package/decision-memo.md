# Decision Memo

## Context

The team needed to prioritize delivery of the core Evergreen Quote experience within a limited timeframe.

## Options Considered

1. Focus first on visual enhancements and testimonials.

2. Focus first on the quote form, responsiveness, and core user experience.

## Recommendation

Prioritize assembly of the quote experience, responsiveness, and navigation before less critical visual enhancements.

## Why

The primary value of Evergreen Quote is allowing prospective customers to obtain a premium estimate quickly. A functioning quote experience delivers customer value, while testimonials and visual enhancements provide secondary benefits.

Day # 3
Use GitHub Copilot for one assembly step. Open VS Code, enable Copilot if it’s not already on, and ask it for help with one small thing — for example, "suggest two more testimonials matching the tone of the existing ones."

    Testimonial 4:
        "Filed a claim on my phone during lunch. Done before my coffe got cold."
        -R Patel, Somerville

    Testamonial 5:
        "Filed a claim on my phone during lunch. Done before my coffee got cold."
         -K. Davis, Dorchester
Critique what it gives you. In one paragraph (~100 words), in your decision memo or as a stretch artifact, answer:
    
    What did Copilot get right? 
        LibertyGPT made it shor and punchy sentences, casual, real-person feel, first initial + las name + local MA city
    
    What did it get wrong? 
        Nothing, everything looks good

    Would you ship its output as-is? 
        Yes
    What would you change?
        Nothing

"LibertyGPT got the tone right — short, punchy sentences with a casual feel and the same name/city format. However, the suggestions lacked specific numbers 
like the original '$40 a month,' which made them feel slightly less authentic. I wouldn't ship as-is because it's missing specific numbers that make 
testimonials feel real. I'd change the town names to better align with my project's target audience."

injections

Leadership Response 
I've reviewed the latest reports and notided two issues. Customer Sucess can reproduce and unexpected renters quote of $8,950/mont for  $25,000 of coverage, and
the CI pipeline is currently failing because the required file assets/rates/renters.json is missing from the latest run. Before we make any assumptions about 
whether these are related, I need the engineering team to assess the impact of the missing asset on quote genration and determine the scope of the customer-facing issue.
The engineering lead owns the investigation and recommendation for next steps, while Customer Success should continue documenting affected scenarios. In the meantime, 
we'll treat this as a potential customer-impacting incident, keep stakeholders informed, and avoid introducing additional changes until we have a clear 
understanding of the risk.

No-go 
We have a confirmed customer-facing defect involving pricing that can be reproduced by Customer Success
The failing CI run was triggered by a change labeled"Hotfix: adjust renters rate," which is directly related to the area where the customer issue is occurring.
Although we do not yet know whether the issues are connected, there is enough uncertainty and potential customer impact that continuing to merge changes would 
increase risk.

What Would Change My Mind
I would move to Go once:

1. Engineering confirms the root cause of the incorrect quote behavior.
2. The impact assessment shows customer risk is understood and mitigated.
3. CI is passing again, including restoration of the missing assets/rates/renters.json file or confirmation that it is no longer required
4. The team provides evidence (testing, validation, or rollback results) that uote generation is functioning correctly.

