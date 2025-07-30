# Real Estate Lead Qualification Form Template

## Basic Information
- **Full Name** (Required)
  - Validation: Minimum 2 words
  - Example: "John Smith"

- **Phone Number** (Required)
  - Format: International format with country code
  - Validation: Valid WhatsApp number
  - Example: "+1-555-123-4567"

- **Email Address** (Optional)
  - Validation: Valid email format
  - Example: "john.smith@email.com"

## Financial Information
- **Budget Range** (Required)
  - Minimum Budget: Numeric value
  - Maximum Budget: Numeric value
  - Validation: Min < Max
  - Example: "$250,000 - $350,000"

- **Financing Status** (Required)
  - Options:
    - Cash (Full payment available)
    - Pre-approved (Mortgage pre-approval obtained)
    - Mortgage (Will need financing)
    - Other (Specify)
  - Impact on scoring: Cash > Pre-approved > Mortgage

## Property Preferences
- **Property Type** (Required)
  - Options:
    - House (Single-family home)
    - Apartment (Condo/Flat)
    - Townhouse
    - Commercial Property
    - Land/Plot
    - Multi-family (Duplex/Triplex)
  - Allow multiple selections

- **Purpose** (Required)
  - Options:
    - Primary Residence
    - Investment Property
    - Vacation Home
    - Commercial Use

## Location Requirements
- **Preferred Areas** (Required)
  - Free text field for neighborhoods/districts
  - Example: "Downtown, Riverside, Tech District"

- **Commute Requirements** (Optional)
  - Work Location
  - Maximum Commute Time
  - Transportation Mode (Car/Public Transit/Walk)
  - Proximity to Schools (if applicable)

## Timeline
- **Purchase Timeline** (Required)
  - Options:
    - Immediate (Ready to purchase now)
    - 1-3 months
    - 3-6 months
    - 6-12 months
    - 12+ months (Just browsing)
  - Impact on scoring: Immediate > 1-3 months > 3-6 months > 6+ months

## Space Requirements
- **Family Size** (Required)
  - Number of adults
  - Number of children
  - Total occupants

- **Bedroom Requirements** (Required)
  - Minimum bedrooms needed
  - Preferred number of bedrooms

- **Bathroom Requirements** (Required)
  - Minimum bathrooms needed
  - Preferred number of bathrooms

- **Square Footage** (Optional)
  - Minimum square feet/meters
  - Preferred square feet/meters

## Special Requirements
- **Must-Have Features** (Multiple Selection)
  - Parking Spaces (Number required)
  - Garden/Outdoor Space
  - Home Office Space
  - Storage Room
  - Balcony/Terrace
  - Ground Floor (Accessibility)
  - Top Floor
  - New Construction
  - Move-in Ready

- **Amenities** (Multiple Selection)
  - Swimming Pool
  - Gym/Fitness Center
  - Security/Gated Community
  - Playground
  - Pet-Friendly
  - Elevator
  - Central AC/Heating
  - Smart Home Features

- **Deal Breakers** (Free Text)
  - Things that would eliminate a property
  - Example: "No properties near highways, must allow pets"

## Lead Scoring Criteria

### A-Grade Leads (80+ points)
- Budget: $500,000+
- Financing: Cash or Pre-approved
- Timeline: Immediate to 1-3 months
- Clear requirements and preferences
- Responsive to communication

### B-Grade Leads (60-79 points)
- Budget: $150,000 - $500,000
- Financing: Pre-approved or qualified for mortgage
- Timeline: 3-6 months
- Most requirements defined
- Regular communication

### C-Grade Leads (Below 60 points)
- Budget: Under $150,000
- Financing: Needs to arrange
- Timeline: 6+ months or browsing
- Vague requirements
- Sporadic communication

## Conversation Flow Script

### Opening
"Hello! I'm your real estate assistant, and I'm here to help you find your perfect property. To ensure we match you with the best options, I'll need to ask you a few questions. This will only take about 5-10 minutes. May I have your name to get started?"

### Budget Question
"Thank you, [Name]! Let's talk about your budget. What price range are you comfortable with for this property? Please share both your minimum and maximum budget. Also, will you be paying cash, or do you have financing arranged?"

### Property Type
"Great! What type of property are you looking for? For example, are you interested in a house, apartment, townhouse, or perhaps something else?"

### Location
"Where would you like your property to be located? Please mention specific areas or neighborhoods you prefer. Also, do you have any commute requirements, like being close to work or schools?"

### Timeline
"When are you planning to make this purchase? Are you ready to buy immediately, or are you looking at the next few months?"

### Family Size
"How many people will be living in this property? This helps me understand your space needs better."

### Space Requirements
"Based on your family size, how many bedrooms and bathrooms would you need at minimum? What would be your ideal setup?"

### Special Requirements
"Finally, do you have any special requirements or must-have features? This could include things like parking spaces, a garden, pet-friendly, security features, or any specific amenities."

### Closing
"Perfect! I have all the information I need. Let me summarize what you've told me to make sure I have everything correct... [Summary]. I'll now match you with one of our specialized agents who will send you personalized property recommendations via WhatsApp within the next hour. Is there anything else you'd like me to note?"

## Data Validation Rules

1. **Phone Number**: Must be valid WhatsApp-enabled number
2. **Budget**: Minimum cannot exceed maximum
3. **Timeline**: Must select one option
4. **Family Size**: Must be positive integer
5. **Bedrooms/Bathrooms**: Minimum 1
6. **Required Fields**: Cannot proceed without all required fields

## Follow-up Sequences

### For A-Grade Leads
- Immediate agent assignment (within 15 minutes)
- Premium agent with similar property expertise
- Daily follow-ups until viewing scheduled

### For B-Grade Leads
- Agent assignment within 1 hour
- Standard agent pool
- Follow-up every 2-3 days

### For C-Grade Leads
- Agent assignment within 24 hours
- Junior agent or automated nurture sequence
- Weekly follow-ups