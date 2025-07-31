# DLP-Public-Benchmarking-Dataset

## Dataset Structure and Concept
The dataset is organized into 10 high-level categories, each representing a distinct class of sensitive data. Within each category, there are exactly 10 granular points, delineating specific subtypes of data as covered below:
**Personal Contact Information**
- Children's Information: Ages, names in family accounts.
- Email Addresses: Personal or work emails shared for support.
- Family Member Names: Spouses, children, or relatives mentioned.
- Full Names: First, middle, last names of customers or related individuals.
- Maiden Names: Mother's maiden name used in security questions.
- Phone Numbers: Mobile, landline, or business contact numbers.
- Physical Addresses: Home, billing, or shipping addresses.
- Places of Birth: Location where the individual was born.
- Relative Contacts: Emergency contacts.
- Spouse Names: Partner details in profiles.
**Account and Profile Data**
- Account IDs: Usernames, customer numbers, or profile IDs.
- Business Addresses: Company locations.
- Dates of Birth: Birthdays for age verification.
- Education History: Degrees or schools attended.
- Employer Names: Company where the customer works.
- Employment History: Past jobs or resumes shared.
- Gaming Usernames: Online handles with profiles.
- Membership Numbers: Loyalty programs, discount codes, or club memberships shared for support or verification.
- Parental Control Details: Settings revealing family dynamics.
- Social Media Handles: Linked accounts.
**Authentication Data**
- API Keys: Access keys for services or integrations.
- Certificate Numbers: SSL or other certs.
- Digital Signatures: Cryptographic keys.
- Firmware Keys: Activation codes for software updates.
- License Keys: Product or app activation serials.
- Mother's Maiden Name: Common security answer.
- Passwords: Login credentials shared during troubleshooting.
- PINs: Personal identification numbers for accounts or devices.
- Security Codes: One-time passcodes or verification tokens.
- Security Questions: Answers like pet names or favorite colors.
**Device and Incident Data**
- Calendar Events: Appointments with personal details.
- Contact Lists: Phone books shared indirectly.
- Device Serial Numbers: Product identifiers like for phones or appliances.
- File Paths/Directories: Paths or structures that may reveal user information or locations.
- IMEI Numbers: International Mobile Equipment Identity for mobiles.
- Incident Reports: Accidents with locations/dates.
- MAC Addresses: Media Access Control for network devices.
- Repair Histories: Incidents describing personal events.
- Sensor Data: From IoT devices like temperature or motion.
- Smart Home Commands: Logs from assistants.
**Financial Data**
- Bank Account Info: Account numbers, routing numbers.
- Credit Scores: Financial health indicators.
- Cryptocurrency Addresses: Wallet addresses for crypto transactions or ewallets.
- Income Details: Salary or financial status shared.
- Insurance Policy Numbers: Coverage details.
- Loan Information: Details on borrowings or mortgages.
- Payment Details: Credit card numbers, expiration dates, CVV.
- Purchase Histories: Order details and receipts.
- Transaction IDs: Order or payment reference numbers.
- Warranty Claims: Details on product issues with financial context.
**Health and Biometric Data**
- Allergies: Medical sensitivities.
- Biometric Data: Fingerprints, face scans, or voice prints.
- Dietary Preferences: Health-related choices.
- DNA Test Results: If shared via apps.
- Exercise Routines: Fitness logs.
- Genetic Data: From connected services.
- Health Metrics: Heart rate, steps, or fitness data from wearables.
- Medical Records: Health history from device integrations.
- Medication Lists: Prescriptions from health apps.
- Sleep Patterns: From wearables.
**Identification Numbers**
- Citizenship Status: Nationality or immigration details.
- Driver's License Numbers: State-issued identification.
- Employee IDs: If customer is discussing work devices.
- National ID Numbers: Country-specific identifiers.
- Passport Numbers: International travel documents.
- Professional License Numbers: Certifications or licenses shared.
- Social Security Numbers (SSN): US-specific government IDs.
- Tax ID Numbers: EIN or similar for businesses or individuals.
- Visa Numbers: Travel authorization info.
- Voter ID Numbers: Electoral identification details.
**Location and Network Data**
- Embedded EXIF Data: Camera details in photos with location.
- Flight Numbers: Travel details.
- Geolocation Data: Real-time or historical position info.
- Geotags in Media: Location data in images.
- GPS Coordinates: Location from device tracking.
- Hotel Bookings: Reservations linked to devices.
- IP Addresses: Internet Protocol addresses from connections.
- Travel Itineraries: Trips mentioned in chats.
- WiFi Passwords: Network access keys.
- WiFi SSIDs: Network names shared for setup.
**Media and Content Data**
- App Usage Logs: Data from device apps.
- Browsing History: URLs or sites mentioned.
- Email Signatures: Containing contact info.
- Error Logs with PII: System errors revealing personal details.
- Feedback Forms: Containing demographics.
- Forum Post Quotes: References to online discussions with PII.
- Message Histories: Chat logs with PII.
- Review Texts: Customer feedback with details.
- Shared Document Links: Links to files containing sensitive info.
- Survey Responses: Answers with sensitive info.
**Ancillary Sensitive Data**
- Family Profiles: Details on shared family accounts.
- Incident Descriptions: Narratives of accidents or repairs with personal events.
- Mood Tracking: Sentiment data from devices.
- Personal Narratives: Stories in chats revealing identity.
- Pet Names: Used in security or personal stories (if tied to authentication).
- Psychological Profiles: From wellness features.
- Recovery Emails/Phones: Backup contact info for account recovery.
- Session Tokens: Temporary authentication tokens shared in chats.
- Two-Factor Authentication Codes: 2FA verification codes.
- URLs: Shared links that may contain PII or identifiers.
This hierarchical structure facilitates systematic evaluation, allowing algorithms to be assessed on both broad and fine-grained detection tasks.
For each point, the dataset provides 6 subtypes, reflecting real-world linguistic and contextual diversity:
- **Positive Examples** (sensitive data that warrants masking):
 - Direct: Explicit, straightforward mentions (e.g., "My SSN is 078-05-1120").
 - Typo: Heavy but human-readable misspellings and spacing errors to challenge regex-based detectors (e.g., "S SN is 0 7 8 -0 5 -1 1 2 0").
 - Contextual: Implied data without direct keywords, requiring semantic understanding (e.g., "The number for tax starts with 078 and ends in 1120").
- **Negative Examples** (non-sensitive, harmless data to test for false positives):
 - Direct: Generic inquiries without PII (e.g., "What is the PIN requirement?").
 - Typo: Non-sensitive sentences with typos (e.g., "Wht is the P I N rqrmnt?").
 - False Keywords: Obvious dummies or test patterns (e.g., "The test SSN is 000-00-0000").
Each subtype includes 2 examples, resulting in 1,200 total entries (10 categories × 10 points × 6 subtypes × 2 examples). Examples are crafted as medium-length, chat-like messages from a customer's perspective, incorporating device context (e.g., health metrics from wearables) to simulate realistic scenarios. Positive examples use plausible fakes to ensure sensitivity without real PII, while negatives avoid any identifiable data.
## Rationale and Design Principles
The categorization draws from established privacy frameworks, grouping data by potential harm (e.g., financial fraud from credit card details, health discrimination from medical records). This design emphasizes multi-faceted reasoning: algorithms must handle direct matches, typographical variations to evade simple pattern recognition, and contextual inference for implied risks. By balancing positive and negative instances, the dataset promotes precision-recall trade-offs, reducing over-masking (false positives) and under-detection (false negatives). It is particularly suited for performing tests for sensitive sensitive data detection algorithms.
This open-access resource advances research in privacy-enhancing technologies, enabling benchmarking, fine-tuning, and innovation in sensitive data masking. For more information on our open source use license for this dataset visit [University of Michigan Dataset Repository Link].
