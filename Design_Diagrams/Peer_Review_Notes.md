# 6. Peer Design Review Notes

## 6.1 Feedback Received

Our design for TradeIO has been reviewed by Harsh Parsana.
The reviewer found the architecture easy to understand and liked the way
that the system is not solely centered around keeping track
of gains and losses, but focuses more on the trading
discipline and behavior analysis.

The distinction between the main risk calculation and AI
analysis was considered as good too.

Some issues that require clarification were found by
the reviewer; these include risk configuration changes,
expiration of account blockage and duplication of trades.

## 6.2 Peer Review Action Items

| ID | Criterion | Issue / Reviewer | Planned Action | Owner | Priority / Due |
| --- | --- | --- | --- | --- | --- |
| PR-01 | Risk | Harsh Parsana: Changing risk settings could allow users to bypass previously reached limits. | Clarify validation and when updated limits become effective. | Samarth | Must-fix; Oct. 16 |
| PR-02 | Clarity | Harsh Parsana: Temporary accountability block expiration needs clearer behavior. | Document how active sessions respond when a block expires. | Ishaa | Must-fix; Oct. 16 |
| PR-03 | Completeness | Harsh Parsana: Manual and broker-imported trades could be counted twice. | Define duplicate detection and trade reconciliation rules. | Samarth | Consider; Oct. 16 |

## 6.3 Summary of Feedback

Feedback was based on issues of risks, clarity, and completeness.
The reviewer thought that our system design was well structured and gave some suggestions on situations that would impact trading responsibility or
accuracy of information.

We will be able to make it clear about risk modifications, temporary blocks expiration,
and avoiding duplicate transactions.

Every criterion had one action item assigned, therefore, none of the categories got more feedback.

## 6.4 Issues We Raised While Reviewing Another Team

**Issue 1 -- Feasibility**

We noticed that the other team's five-minute processing
budget left only 20 seconds of spare time without
measured execution results.

We suggested measuring an actual preprocessing run to
determine whether the timing budget is realistic.

**Issue 2 -- Risk**

We raised a concern about results exceeding the five-minute
deadline because of queue delays.

We recommended saving completed results with an
over-time flag so delayed processing would not cause
results to be lost.
