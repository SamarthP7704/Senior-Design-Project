# TradeIO – User Stories and Use Cases

## Team Members

- Ishaa Jain
- Samarth Prajapati

---

# Stakeholder Map

TradeIO has stakeholders who directly use the system, people who interact with or support those users, and others whose needs may not be immediately visible during development.

## Primary Stakeholders

- **Individual Traders:** Traders who use TradeIO to record trades, review performance, understand their trading behavior, and improve their trading discipline.
- **Samarth Prajapati:** Samarth is both a member of the development team and an intended TradeIO user. He trades using USD, and his experience as a trader provides a direct user perspective during development and testing.
- **International Traders:** Some intended TradeIO users, including Ishaa's father and Samarth's father, are located in India and use INR. Their needs helped identify requirements related to currencies, time zones, markets, and providing a consistent experience across regions.

## Secondary Stakeholders

- **Accountability Partners:** People selected by traders to help them stay accountable to trading limits they set for themselves. With prior permission from the trader, an accountability partner may also apply a temporary TradeIO cooldown after problematic trading behavior is detected. Ishaa will act as Samarth's accountability partner when testing this functionality.
- **Development and Administration Team:** Ishaa Jain and Samarth Prajapati are responsible for developing, maintaining, testing, and administering TradeIO.

## Hidden Stakeholders

- **Traders with privacy and security needs:** TradeIO may contain financial information, trading history, journal entries, emotions, and trading mistakes. Traders need this information to remain protected from people who do not need access to it.
- **Traders with accessibility needs:** Some traders may rely on keyboard navigation, screen readers, or other assistive technologies. Core TradeIO functions should remain usable without depending on a single method of interaction.
- **Traders using different brokers:** Traders may use different brokerage platforms and may want to connect their brokerage account to TradeIO instead of entering every trade manually.
- **Traders in different markets and regions:** Traders may use different currencies, time zones, instruments, and markets. TradeIO should not assume that every trader operates in the same trading environment.

---

# How We Identified User Needs

We gathered input from people who trade or are familiar with trading, including Samarth, Ishaa's father, Samarth's father, and a friend of Ishaa's father.

We used two elicitation techniques.

## 1. Informal Interviews and Discussions

We talked with Ishaa's father, Samarth's father, and a friend of Ishaa's father about their trading experiences. We discussed how they keep track of trades, review their performance, manage trading decisions, and some of the problems they experience while trading.

These discussions helped us identify differences between trading environments. Ishaa's father and Samarth's father are located in India and use INR, while Samarth currently trades using USD. Although these traders operate in different environments, they want the process of recording and reviewing trades to remain consistent and straightforward.

Privacy and convenience are also important requirements for TradeIO. Traders need their financial and behavioral information to remain protected while still having the option to connect TradeIO to a supported broker so that available trade information can be brought into the journal without requiring every trade to be entered manually.

## 2. Observation

We observed Samarth's trading workflow and how he approaches trading and reviews his activity. Since Samarth is both a trader and a member of the TradeIO development team, this gave us a direct view of the steps involved in trading and some of the difficulties involved in consistently recording trades, reviewing performance, and recognizing behavioral patterns.

The observation also helped us consider how accountability could go beyond simply showing statistics. A trader may recognize that they tend to continue trading after reaching a limit but still choose to continue. TradeIO therefore considers accountability features that the trader can voluntarily enable beforehand, including alerts to an accountability partner and temporary cooldowns.

From these interviews, observations, and project discussions, we identified several recurring needs:

- Maintaining an accurate trading history
- Understanding why trades were successful or unsuccessful
- Recognizing repeated trading and behavioral mistakes
- Managing overtrading and accountability
- Supporting different currencies and time zones
- Protecting private trading and financial information
- Reducing unnecessary manual trade entry through supported broker connections
- Providing a consistent experience for traders in different regions
- Providing optional accountability controls without giving another person unrestricted access to the trader's information

We also considered stakeholders whose needs may not appear during our initial interviews and observations. This includes traders who use assistive technologies and traders who use brokers or trading environments different from those used by our initial stakeholders.

---

# User Stories

## US-01 – Record and Review Trading Activity

**Stakeholder Category:** Primary

As an **individual trader**,  
I want to **maintain an accurate record of my trades and review my trading history**,  
so that I can **understand my performance over time and learn from previous trades**.

---

## US-02 – Understand Trading Behavior

**Stakeholder Category:** Primary

As a **trader trying to improve**,  
I want to **identify patterns in my trading decisions and behavior**,  
so that I can **recognize repeated mistakes and improve my trading discipline**.

---

## US-03 – Support Trader Accountability

**Stakeholder Category:** Secondary

As an **accountability partner**,  
I want to **receive an alert when the trader I support exceeds their self-defined daily trade limit and, when previously authorized by the trader, apply a temporary TradeIO cooldown**,  
so that I can **help the trader step away from repeated or impulsive trading behavior**.

---

## US-04 – Securely Connect Trading Information

**Stakeholder Category:** Hidden

As a **trader using a supported broker**,  
I want to **securely connect my brokerage account and import supported trade information**,  
so that I can **reduce manual trade entry without unnecessarily exposing my private financial information**.

---

## US-05 – Support Different Trading Environments

**Stakeholder Category:** Hidden

As a **trader operating in a different market or region**,  
I want TradeIO to **use my selected currency and time zone when recording and presenting my trading activity**,  
so that I can **use the system consistently without having to manually adjust my trading information for another region**.

---

# INVEST Self-Check

We reviewed the five user stories using the INVEST criteria to make sure each story is suitable for continued design and development.

| INVEST Principle | What We Checked | How Our Stories Meet It |
|---|---|---|
| **I – Independent** | Can the story provide value without depending completely on another story? | Each story represents a separate need, such as trade tracking, behavior analysis, accountability, broker connectivity, or regional support. |
| **N – Negotiable** | Does the story describe the need without requiring one exact implementation? | The stories describe what stakeholders need without requiring specific screens, buttons, technologies, or APIs. |
| **V – Valuable** | Does the story provide a clear benefit to a stakeholder? | Each story includes a "so that" statement explaining why the capability matters to the stakeholder. |
| **E – Estimable** | Is the story clear enough for the team to understand and estimate the work? | Each story identifies a specific stakeholder, goal, and expected benefit, allowing the team to estimate the work as the design becomes more detailed. |
| **S – Small** | Is the story focused on one manageable stakeholder need? | Each story focuses on one main area of TradeIO rather than attempting to describe the entire system. |
| **T – Testable** | Can we determine whether the stakeholder's need has been satisfied? | Each story describes an observable outcome that can later be verified through acceptance criteria and testing. |

**Self-Check Result:** We reviewed US-01 through US-05 using the INVEST criteria above. All five stories meet the criteria at the current requirements stage. UC-01 and UC-02 below provide detailed acceptance criteria for two of the stories.

---

# Use Cases

## UC-01 – Connect a Broker and Import Trades

**Expands:** US-04

### Primary Actor

Trader

### Secondary Actors

- TradeIO
- Supported Broker

### Preconditions

1. The trader has a TradeIO account.
2. The trader is signed in.
3. The trader has an account with a broker supported by TradeIO.
4. The supported broker allows the trader to authorize access to supported trading information.

### Main Success Flow

1. **Trader:** Starts the process of connecting a supported brokerage account.
2. **TradeIO:** Directs the trader through the broker's required authorization process.
3. **Trader:** Authorizes access to the supported trading information.
4. **Supported Broker:** Confirms the authorization.
5. **TradeIO:** Establishes the authorized broker connection.
6. **Trader:** Requests available trade information from the connected broker.
7. **TradeIO:** Retrieves the supported trade information.
8. **TradeIO:** Associates the retrieved trades with the correct trader account.
9. **TradeIO:** Stores the supported trade information without requiring the trader to manually re-enter the imported trade details.
10. **Trader:** Reviews the imported trades in their trading history.

### Alternate Flow – Manual Trade Entry

1. The trader does not connect a brokerage account or uses a broker that is not currently supported.
2. The trader chooses to record a trade manually.
3. TradeIO requests the required trade information.
4. The trader enters the required trade details.
5. TradeIO validates and saves the trade.
6. The manually recorded trade becomes available in the trader's trading history.

### Exception Flow – Broker Authorization Is Not Completed

1. The trader starts the broker connection process.
2. The required broker authorization is denied, canceled, or not completed.
3. TradeIO does not establish the broker connection.
4. No trade information is imported from the broker.
5. The trader's existing TradeIO information remains unchanged.
6. The trader can continue using manual trade entry.

### Postcondition

If authorization succeeds, the supported brokerage account is connected to the correct TradeIO account and supported trade information can be imported. If authorization does not succeed, no broker connection is established and the trader can continue using TradeIO through manual trade entry.

---

# UC-01 Acceptance Criteria

## AC-01.1 – Successful Broker Connection

**Given** a signed-in trader has an account with a broker supported by TradeIO,  
**When** the trader successfully completes the broker's required authorization process,  
**Then** TradeIO associates exactly one authorized broker connection with the correct TradeIO account.

## AC-01.2 – Import Supported Trades

**Given** a trader has successfully connected a supported brokerage account,  
**When** the trader requests available supported trade information,  
**Then** the retrieved trades are associated with that trader's TradeIO account and become available in the trader's trading history without requiring the imported trade details to be manually re-entered.

## AC-01.3 – Broker Authorization Not Completed

**Given** a trader starts the broker connection process,  
**When** the required authorization is denied, canceled, or not completed,  
**Then** no broker connection is created, no broker trade information is imported, and the trader's existing TradeIO data remains unchanged.

---

# UC-02 – Apply an Accountability Cooldown

**Expands:** US-03

### Primary Actor

Accountability Partner

### Secondary Actor

Trader

### Preconditions

1. The trader has a TradeIO account.
2. The trader has configured a self-defined daily trade limit.
3. TradeIO can determine whether the trader has exceeded the configured daily trade limit.
4. TradeIO can determine whether the trader has configured an accountability partner.
5. If an accountability partner exists, TradeIO can determine whether the trader previously granted that partner permission to apply temporary cooldowns.

### Main Success Flow

1. **Trader:** Exceeds the self-defined daily trade limit.
2. **TradeIO:** Detects that the daily limit has been exceeded.
3. **TradeIO:** Records the limit-exceeded event.
4. **TradeIO:** Determines that the trader has a configured accountability partner.
5. **TradeIO:** Sends an accountability alert to the configured accountability partner.
6. **Accountability Partner:** Receives the alert and chooses to apply a temporary cooldown.
7. **Accountability Partner:** Selects a cooldown duration between 10 minutes and 24 hours.
8. **TradeIO:** Confirms that the accountability partner has permission to apply a cooldown.
9. **TradeIO:** Confirms that the selected duration is within the allowed range.
10. **TradeIO:** Activates the temporary cooldown.
11. **Trader:** Is informed that an accountability cooldown is active, who initiated it, and when it will expire.
12. **TradeIO:** Restricts the actions covered by the cooldown while continuing to allow the trader to access permitted account information.
13. **TradeIO:** Automatically removes the restriction when the cooldown period expires.

### Alternate Flow – Accountability Partner Does Not Apply a Cooldown

1. TradeIO sends the accountability alert after the trader exceeds the configured limit.
2. The accountability partner receives the alert.
3. The accountability partner chooses not to apply a cooldown.
4. TradeIO does not activate a cooldown.
5. The trader's account remains available without an accountability restriction.
6. The limit-exceeded event remains recorded.

### Exception Flow – No Accountability Partner Configured

1. **Trader:** Exceeds the self-defined daily trade limit.
2. **TradeIO:** Detects that the daily limit has been exceeded.
3. **TradeIO:** Records the limit-exceeded event.
4. **TradeIO:** Determines that the trader has not configured an accountability partner.
5. **TradeIO:** Does not generate an external accountability alert or make a cooldown available to another person.
6. **Trader:** Receives the normal TradeIO warning that the configured daily limit has been exceeded.
7. **TradeIO:** Keeps the limit-exceeded event in the trader's account.

### Exception Flow – Accountability Partner Does Not Have Cooldown Permission

1. The trader exceeds the configured daily trade limit.
2. TradeIO records the limit-exceeded event.
3. TradeIO sends an accountability alert to the configured accountability partner.
4. The accountability partner receives the alert and attempts to apply a cooldown.
5. TradeIO determines that the trader has not granted cooldown permission to that accountability partner.
6. TradeIO rejects the cooldown request.
7. The trader's account remains unrestricted by the accountability partner.

### Exception Flow – Invalid Cooldown Duration

1. An authorized accountability partner attempts to apply a cooldown.
2. The requested duration is shorter than 10 minutes or longer than 24 hours.
3. TradeIO rejects the requested duration.
4. No cooldown is activated.
5. The accountability partner may select a valid duration between 10 minutes and 24 hours.

### Postcondition

If an authorized accountability partner selects a valid duration, a temporary TradeIO cooldown is active for the selected period and expires automatically.

If the trader has no accountability partner, the limit-exceeded event is still recorded and the trader receives the normal TradeIO warning, but no external accountability alert or cooldown is generated.

The accountability role does not give the partner access to the trader's private trades, journal entries, financial information, broker credentials, or other protected information.

The cooldown applies only to selected actions within TradeIO. It does not prevent the trader from placing trades directly through an external brokerage platform.

---

# UC-02 Acceptance Criteria

## AC-02.1 – Accountability Alert

**Given** a trader has a configured accountability partner and has exceeded their self-defined daily trade limit,  
**When** TradeIO records the limit-exceeded event,  
**Then** exactly one accountability alert is generated for the configured accountability partner.

## AC-02.2 – Authorized Cooldown

**Given** the trader has previously authorized the accountability partner to apply temporary cooldowns,  
**When** the accountability partner selects a duration between 10 minutes and 24 hours,  
**Then** TradeIO activates one cooldown for the selected duration and records its start time, expiration time, and the accountability partner who initiated it.

## AC-02.3 – Automatic Expiration

**Given** an accountability cooldown is active,  
**When** the selected cooldown duration expires,  
**Then** TradeIO automatically removes the temporary restriction without requiring action from the trader or accountability partner.

## AC-02.4 – No Cooldown Permission

**Given** an accountability partner is configured but has not been granted cooldown permission by the trader,  
**When** the accountability partner attempts to apply a cooldown,  
**Then** TradeIO rejects the request and does not place an accountability restriction on the trader's account.

## AC-02.5 – Invalid Cooldown Duration

**Given** an accountability partner is authorized to apply cooldowns,  
**When** the partner requests a duration shorter than 10 minutes or longer than 24 hours,  
**Then** TradeIO rejects the duration and does not activate the cooldown.

## AC-02.6 – Trader Privacy During Accountability

**Given** a person is configured as a trader's accountability partner,  
**When** that person receives an accountability alert or applies an authorized cooldown,  
**Then** the accountability role does not provide access to the trader's private journal entries, broker credentials, or private financial information.

## AC-02.7 – No Accountability Partner Configured

**Given** a trader has not configured an accountability partner,  
**When** the trader exceeds their self-defined daily trade limit,  
**Then** TradeIO records exactly one limit-exceeded event, does not generate an accountability-partner alert, and does not allow another person to initiate an accountability cooldown.
