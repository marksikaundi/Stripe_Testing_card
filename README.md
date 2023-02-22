# DOCUMENTATIONS FOR PAYMENT TEST_MODE
<hr>Stripe_Testing_card
Stripe Testing payments
- https://stripe.com/docs/testing
Testing
Simulate payments to test your integration.
NOT A DEVELOPER?
Check out our no-code docs, use a prebuilt solution from our partner directory, or hire a Stripe-certified expert.

To confirm that your integration works correctly, simulate transactions without moving any money, using special values in test mode.

Test cards let you simulate several scenarios:

Successful payments by card brand or country
Card errors due to declines, fraud, or invalid data
Disputes and refunds
Authentication with 3D Secure and PINs
Testing non-card payments works similarly. Each payment method has its own special values.

Because of rate limits, we don’t recommend using test mode to load-test your integration. Instead, see our documentation on load testing.

How to use test cards
Any time you work with a test card, use test API keys in all API calls. This is true whether you’re serving a payment form to test interactively or writing test code.

Do not use real card details. Testing in live mode using real payment method details is prohibited by the Stripe Services Agreement. Use your test API keys and the card numbers below.

Testing interactively
When testing interactively, use a card number, such as 4242 4242 4242 4242. Enter the card number in the Dashboard or in any payment form.

Use a valid future date, such as 12/34.
Use any three-digit CVC (four digits for American Express cards).
Use any value you like for other form fields.
An example payment form showing how to enter a test card number. The card number is "4242 4242 4242 4242", the expiration date is "12/34", and the CVC is "567". Other fields have arbitrary values. For instance, the email address is "test@example.com"
Testing a form interactively with the test card number 4242 4242 4242 4242

Test code
When writing test code, we don’t recommend using a card number. Instead, use the corresponding PaymentMethod, such as pm_card_visa.


curl

Stripe CLI

Ruby

Python

PHP

Java

Node

Go

.NET
Command Line


curl https://api.stripe.com/v1/payment_intents \
  -u sk_test_4eC39HqLyjWDarjtT1zdp7dc: \
  -d amount=500 \
  -d currency=gbp \
  -d payment_method=pm_card_visa
We don’t recommend using card numbers directly in API calls or server-side code, even in test mode. If you do use them, your code might not be PCI-compliant when you go live.

Most integrations don’t use Tokens anymore, but we make test Tokens such as tok_visa available if you need them.

When you’re ready to take your integration live, replace your test publishable and secret API keys with live ones. You can’t process live payments if your integration is still using your test API keys.

Cards by brand
To simulate a successful payment, use test cards from the following list. The billing country for each test card is set to the United States. If you need to create test card payments using cards for other billing countries, use international test cards.


Card numbers

PaymentMethods

Tokens
BRAND	NUMBER	CVC	DATE
Filter...
Visa	4242424242424242	Any 3 digits	Any future date
Visa (debit)	4000056655665556	Any 3 digits	Any future date
Mastercard	5555555555554444	Any 3 digits	Any future date
Mastercard (2-series)	2223003122003222	Any 3 digits	Any future date
Mastercard (debit)	5200828282828210	Any 3 digits	Any future date
Mastercard (prepaid)	5105105105105100	Any 3 digits	Any future date
American Express	378282246310005	Any 4 digits	Any future date
American Express	371449635398431	Any 4 digits	Any future date
Discover	6011111111111117	Any 3 digits	Any future date
Discover	6011000990139424	Any 3 digits	Any future date
Discover (debit)	6011981111111113	Any 3 digits	Any future date
Diners Club	3056930009020004	Any 3 digits	Any future date
Diners Club (14-digit card)	36227206271667	Any 3 digits	Any future date
JCB	3566002020360505	Any 3 digits	Any future date
UnionPay	6200000000000005	Any 3 digits	Any future date
Most Cartes Bancaires cards are co-branded with either Visa or Mastercard. The test cards in the following table simulate successful payments with co-branded cards.

BRAND/CO-BRAND	NUMBER	CVC	DATE
Cartes Bancaires/Visa	4000002500001001	Any 3 digits	Any future date
Cartes Bancaires/Mastercard	5555552500001001	Any 3 digits	Any future date
Cards by country
To simulate successful payments from many countries, use test cards from the following sections.

Americas
Use these test cards to simulate successful payments from North and South America.


Card numbers

PaymentMethods

Tokens
COUNTRY	NUMBER	BRAND
Filter...
United States (US)	4242424242424242	Visa
Brazil (BR)	4000000760000002	Visa
Canada (CA)	4000001240000000	Visa
Mexico (MX)	4000004840008001	Visa
Europe and Middle East
Use these test cards to simulate successful payments from Europe and the Middle East.

Strong Customer Authentication regulations require 3D Secure authentication for online payments within the European Economic Area. The test cards in this section simulate a payment that succeeds without authentication. We recommend also testing scenarios that involve authentication, using 3D Secure test cards.


Card numbers

PaymentMethods

Tokens
COUNTRY	NUMBER	BRAND
Filter...
United Arab Emirates (AE)	4000007840000001	Visa
United Arab Emirates (AE)	5200007840000022	Mastercard
Austria (AT)	4000000400000008	Visa
Belgium (BE)	4000000560000004	Visa
Bulgaria (BG)	4000001000000000	Visa
Belarus (BY)	4000001120000005	Visa
Croatia (HR)	4000001910000009	Visa
Cyprus (CY)	4000001960000008	Visa
Czech Republic (CZ)	4000002030000002	Visa
Denmark (DK)	4000002080000001	Visa
Estonia (EE)	4000002330000009	Visa
Finland (FI)	4000002460000001	Visa
France (FR)	4000002500000003	Visa
Germany (DE)	4000002760000016	Visa
Gibraltar (GI)	4000002920000005	Visa
Greece (GR)	4000003000000030	Visa
Hungary (HU)	4000003480000005	Visa
Ireland (IE)	4000003720000005	Visa
Italy (IT)	4000003800000008	Visa
Latvia (LV)	4000004280000005	Visa
Liechtenstein (LI)	4000004380000004	Visa
Lithuania (LT)	4000004400000000	Visa
Luxembourg (LU)	4000004420000006	Visa
Malta (MT)	4000004700000007	Visa
Netherlands (NL)	4000005280000002	Visa
Norway (NO)	4000005780000007	Visa
Poland (PL)	4000006160000005	Visa
Portugal (PT)	4000006200000007	Visa
Romania (RO)	4000006420000001	Visa
Saudi Arabia (SA)	4000006820000007	Visa
Slovenia (SI)	4000007050000006	Visa
Slovakia (SK)	4000007030000001	Visa
Spain (ES)	4000007240000007	Visa
Sweden (SE)	4000007520000008	Visa
Switzerland (CH)	4000007560000009	Visa
United Kingdom (GB)	4000008260000000	Visa
United Kingdom (GB)	4000058260000005	Visa (debit)
United Kingdom (GB)	5555558265554449	Mastercard
Asia-Pacific
Use these test cards to simulate successful payments from Asia and the Pacific.


Card numbers

PaymentMethods

Tokens
COUNTRY	NUMBER	BRAND
Filter...
Australia (AU)	4000000360000006	Visa
China (CN)	4000001560000002	Visa
Hong Kong (HK)	4000003440000004	Visa
India (IN)	4000003560000008	Visa
Japan (JP)	4000003920000003	Visa
Japan (JP)	3530111333300000	JCB
Malaysia (my)	4000004580000002	Visa
New Zealand (NZ)	4000005540000008	Visa
Singapore (SG)	4000007020000003	Visa
Thailand (TH)	4000007640000003	Visa (credit)
Thailand (TH)	4000057640000008	Visa (debit)
Declined payments
To simulate payments that the issuer declines for various reasons, use test cards from this section. This can be useful for testing your integration’s error handling logic. Using one of these cards results in a card error with the given error code and decline code.

To simulate an incorrect CVC decline, you must provide a CVC. It can be any three-digit number. If you don’t provide a CVC, Stripe doesn’t perform the CVC check, so the check can’t fail.


Card numbers

Payment Method

Tokens
DESCRIPTION	NUMBER	ERROR CODE	DECLINE CODE
Filter...
Generic decline	4000000000000002	card_declined	generic_decline
Insufficient funds decline	4000000000009995	card_declined	insufficient_funds
Lost card decline	4000000000009987	card_declined	lost_card
Stolen card decline	4000000000009979	card_declined	stolen_card
Expired card decline	4000000000000069	expired_card	n/a
Incorrect CVC decline	4000000000000127	incorrect_cvc	n/a
Processing error decline	4000000000000119	processing_error	n/a
Incorrect number decline	4242424242424241	incorrect_number	n/a
The cards in the previous table can’t be attached to a Customer object. To simulate a declined payment with a successfully attached card, use the next one.

DESCRIPTION	NUMBER	DETAILS
Decline after attaching	4000000000000341	Attaching this card to a Customer object succeeds, but attempts to charge the customer fail.
Fraud prevention
Stripe’s fraud prevention system, Radar, can block payments when they have a high risk level or fail verification checks. You can use the cards in this section to test your Radar settings. You can also use them to test how your integration responds to blocked payments.

Each card simulates specific risk factors. Your Radar settings determine which risk factors cause it to block a payment. Blocked payments result in card errors with an error code of fraud.

To simulate a failed CVC check, you must provide a CVC. It can be any three-digit number. To simulate a failed postal code check, you must provide a postal code. It can be any valid postal code. If you don’t provide those values, Radar doesn’t perform the corresponding checks, so the checks can’t fail.


Card numbers

PaymentMethods

Tokens
DESCRIPTION	NUMBER	DETAILS
Filter...
Always blocked

4100000000000019	
The charge has a risk level of “highest”

Radar always blocks it.

Highest risk

4000000000004954	
The charge has a risk level of “highest”

Radar might block it depending on your settings.

Elevated risk

4000000000009235	
The charge has a risk level of “elevated”

If you use Radar for Fraud Teams, Radar might queue it for review.

CVC check fails

4000000000000101	
If you provide a CVC number, the CVC check fails.

Radar might block it depending on your settings.

Postal code check fails

4000000000000036	
If you provide a postal code, the postal code check fails.

Radar might block it depending on your settings.

Line1 check fails

4000000000000028	
The address line 1 check fails.

The payment succeeds unless you block it with a custom Radar rule.

Address checks fail

4000000000000010	
The address postal code check and address line 1 check both fail.

Radar might block it depending on your settings.

Address unavailable

4000000000000044	
The address postal code check and address line 1 check are both unavailable.

The payment succeeds unless you block it with a custom Radar rule.

Invalid data
To test errors resulting from invalid data, provide invalid details. You don’t need a special test card for this. Any invalid value works. For instance:

invalid_expiry_month: Use an invalid month, such as 13
invalid_expiry_year: Use a year in the past, such as 70
invalid_cvc: Use a two-digit number, such as 99
incorrect_number: Use a card number that fails the Luhn check, such as 4242424242424241
Disputes
To simulate a disputed transaction, use the test cards in this section. Then, to simulate winning or losing the dispute, provide winning or losing evidence.


Card numbers

PaymentMethods

Tokens
DESCRIPTION	NUMBER	DETAILS
Fraudulent	4000000000000259	With default account settings, charge succeeds, only to be disputed as fraudulent. This type of dispute is protected after 3D Secure authentication.
Not received	4000000000002685	With default account settings, charge succeeds, only to be disputed as product not received. This type of dispute isn’t protected after 3D Secure authentication.
Inquiry	4000000000001976	With default account settings, charge succeeds, only to be disputed as an inquiry.
Warning	4000000000005423	With default account settings, charge succeeds, only to receive an early fraud warning.
Evidence
To simulate winning or losing the dispute, respond with one of the evidence values from the table below.

If you respond using the API, pass the value from the table as uncategorized_text.
If you respond in the Dashboard, enter the value from the table in the Additional information field. Then, click Submit evidence.
EVIDENCE	DESCRIPTION
winning_evidence	The dispute is closed and marked as won. Your account is credited the amount of the charge and related fees.
losing_evidence	The dispute is closed and marked as lost. Your account isn’t credited.
Refunds
In live mode, refunds are asynchronous: a refund can appear to succeed and later fail, or can appear as pending at first and later succeed. To simulate refunds with those behaviors, use the test cards in this section. (With all other test cards, refunds succeed immediately and don’t change status after that.)


Card numbers

PaymentMethods

Tokens
DESCRIPTION	NUMBER	DETAILS
Asynchronous success	4000000000007726	The charge succeeds. If you initiate a refund, its status begins as pending. Some time later, its status transitions to succeeded and sends a charge.refund.updated webhook event.
Asynchronous failure	4000000000005126	The charge succeeds. If you initiate a refund, its status begins as succeeded. Some time later, its status transitions to failed and sends a charge.refund.updated webhook event.
Available balance
To send the funds from a test transaction directly to your available balance, use the test cards in this section. Other test cards send funds from a successful payment to your pending balance.


Card numbers

PaymentMethods

Tokens
DESCRIPTION	NUMBER	DETAILS
Bypass pending balance	4000000000000077	The US charge succeeds. Funds are added directly to your available balance, bypassing your pending balance.
Bypass pending balance	4000003720000278	The international charge succeeds. Funds are added directly to your available balance, bypassing your pending balance.
3D Secure authentication
3D Secure requires an additional layer of authentication for credit card transactions. Use the test cards in this section to simulate payment flows that involve authentication. Other test cards are not enrolled in 3D Secure, which means that no authentication can occur.

3D Secure redirects won’t occur for payments created directly in the Stripe Dashboard. Instead, use your integration’s own frontend or an API call.

Authentication and setup
To simulate payment flows that include authentication, use the test cards in this section. Some of these cards can also be set up for future payments, or have already been.


Card numbers

PaymentMethods
DESCRIPTION	NUMBER	DETAILS
Filter...
Authenticate unless set up	4000002500003155	This card requires authentication for off-session payments unless you set it up for future payments. After you set it up, off-session payments no longer require authentication.
Always authenticate	4000002760003184	This card requires authentication on all transactions, regardless of how the card is set up.
Already set up	4000003800000446	This card is already set up for off-session use. It requires authentication for one-time and other on-session payments. However, all off-session payments succeed as if the card has been previously set up.
Insufficient funds	4000008260003178	This card requires authentication for one-time payments. All payments are declined with an insufficient_funds failure code even after being successfully authenticated or previously set up.
Support and availability
Stripe requests authentication when required by regulation, or when triggered by your Radar rules or custom code. Even if authentication is requested, it can’t always be performed—for instance, the customer’s card might not be enrolled, or an error might occur. Use the test cards in this section to simulate various combinations of these factors.


Card numbers

PaymentMethods

Tokens
3D SECURE USAGE	OUTCOME	NUMBER	DETAILS
Filter...
3DS2 Required	OK	4000000000003220	3D Secure 2 authentication must be completed for the payment to be successful. By default, your Radar rules request 3D Secure authentication for this card.
3DS Required	OK	4000000000003063	3D Secure authentication must be completed for the payment to be successful. By default, your Radar rules request 3D Secure authentication for this card.
3DS Required	Declined	4000008400001629	3D Secure authentication is required, but payments are declined with a card_declined failure code after authentication. By default, your Radar rules request 3D Secure authentication for this card.
3DS Required	Error	4000008400001280	3D Secure authentication is required, but the 3D Secure lookup request fails with a processing error. Payments are declined with a card_declined failure code. By default, your Radar rules request 3D Secure authentication for this card.
3DS Supported	OK	4000000000003055	3D Secure authentication might still be performed, but isn’t required. By default, your Radar rules don’t request 3D Secure authentication for this card.
3DS Supported	Error	4000000000003097	3D Secure authentication might still be performed, but isn’t required. However, attempts to perform 3D Secure result in a processing error. By default, your Radar rules don’t request 3D Secure authentication for this card.
3DS Supported	Unenrolled	4242424242424242	3D Secure is supported for this card, but this card isn’t enrolled in 3D Secure. This means that if your Radar rules request 3D Secure, the customer doesn’t go through additional authentication. By default, your Radar rules don’t request 3D Secure authentication for this card.
3DS Not supported	378282246310005	3D Secure isn’t supported on this card and can’t be invoked. The PaymentIntent proceeds without performing authentication.
3D Secure mobile challenge flows
In a mobile payment, several challenge flows for authentication—where the customer has to interact with prompts in the UI—are available. Use the test cards in this section to trigger a specific challenge flow for test purposes. These cards aren’t useful in browser-based payment forms or in API calls. In those environments, they work but don’t trigger any special behavior. Because they’re not useful in API calls, we don’t provide any PaymentMethod or Token values to test with.

CHALLENGE FLOW	NUMBER	DETAILS
Filter...
Out of band	4000000000003220	3D Secure 2 authentication must be completed on all transactions. Triggers the challenge flow with Out of Band UI.
One time passcode	4000000000003238	3D Secure 2 authentication must be completed on all transactions. Triggers the challenge flow with One Time Passcode UI.
Single select	4000000000003246	3D Secure 2 authentication must be completed on all transactions. Triggers the challenge flow with single-select UI.
Multi select	4000000000003253	3D Secure 2 authentication must be completed on all transactions. Triggers the challenge flow with multi-select UI.
Webview	4000000000003063	3D Secure authentication must be completed for the payment to be successful. Triggers the challenge flow using a webview. You can check that your return_url dismisses the modal.
Payments with PINs
Use the test cards in this section to simulate successful in-person payments where a PIN is involved.

There are many other options for testing in-person payments, including a simulated reader and physical test cards. See Test Stripe Terminal for more information.


Card numbers

PaymentMethods
DESCRIPTION	NUMBER	DETAILS
Offline PIN	4001007020000002	This card simulates a payment where the cardholder is prompted for and enters an offline PIN. The resulting charge has cardholder_verification_method set to offline_pin.
Offline PIN retry	4000008260000075	Simulates an SCA-triggered retry flow where a cardholder’s initial contactless charge fails and the reader then prompts the user to insert their card and enter their offline PIN. The resulting charge has cardholder_verification_method set to offline_pin.
Online PIN	4001000360000005	This card simulates a payment where the cardholder is prompted for and enters an online PIN. The resulting charge has cardholder_verification_method set to online_pin.
Online PIN retry	4000002760000008	Simulates an SCA-triggered retry flow where a cardholder’s initial contactless charge fails and the reader then prompts the user to insert their card and enter their online PIN. The resulting charge has cardholder_verification_method set to online_pin.
Webhooks
To test webhooks, you have two options:

Perform actions in test mode that send legitimate events to your endpoint. For instance, to trigger the charge.succeeded event, you can use a test card that produces a successful charge.
Trigger events using the Stripe CLI or using Stripe for Visual Studio Code.
Rate limits
If your requests in test mode begin to receive 429 HTTP errors, make them less frequently. These errors come from our rate limiter, which is stricter in test mode than in live mode.

We don’t recommend load testing your integration using the Stripe API in test mode. Because the load limiter is stricter in test mode, you might see errors that you wouldn’t see in production. See our documentation on load testing for an alternative approach.

Non-card payments
Any time you use a test non-card payment method, use test API keys in all API calls. This is true whether you’re serving a payment form you can test interactively or writing test code.

Different payment methods have different test procedures:


ACH Direct Debit

SEPA debit

BECS

Link

Redirects

Others
To test scenarios with instant verifications, mimic different scenarios for ACH charges by selecting the test bank account for the use case you want to test.

Send transaction emails in test mode
After you collect the bank account details and accept a mandate, send the mandate confirmation and microdeposit verification emails in test mode. To do this, provide an email in the payment_method_data.billing_details[email] field in the form of {any-prefix}+test_email@{any_domain} when you collect the payment method details.

You need to activate your Stripe account before you can trigger these emails in Test mode.

Test account numbers
Stripe provides several test account numbers and corresponding tokens you can use to make sure your integration for manually-entered bank accounts is ready for production.

ACCOUNT NUMBER	TOKEN	ROUTING NUMBER	BEHAVIOR
000123456789	pm_usBankAccount_success	110000000	The payment succeeds.
000111111113	pm_usBankAccount_accountClosed	110000000	The payment fails because the account is closed.
000111111116	pm_usBankAccount_noAccount	110000000	The payment fails because no account is found.
000222222227	pm_usBankAccount_insufficientFunds	110000000	The payment fails due to insufficient funds.
000333333335	pm_usBankAccount_debitNotAuthorized	110000000	The payment fails because debits aren’t authorized.
000444444440	pm_usBankAccount_invalidCurrency	110000000	The payment fails due to invalid currency.
000666666661	pm_usBankAccount_failMicrodeposits	110000000	The payment fails to send microdeposits.
Before test transactions can complete, you need to verify all test accounts that automatically succeed or fail the payment. To do so, use the test microdeposit amounts or descriptor codes below.

Test microdeposit amounts and descriptor codes
To mimic different scenarios, use these microdeposit amounts or 0.01 descriptor code values.

MICRODEPOSIT VALUES	0.01 DESCRIPTOR CODE VALUES	SCENARIO
32 and 45	SM11AA	Simulates verifying the account.
10 and 11	SM33CC	Simulates exceeding the number of allowed verification attempts.
40 and 41	SM44DD	Simulates a microdeposit timeout.
See also
Testing your Connect integration
Testing Stripe Billing
Testing Stripe Terminal
Load testing
Was this page helpful?
