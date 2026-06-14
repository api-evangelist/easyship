# EasyShip GraphQL Schema

## Overview

This document describes a conceptual GraphQL schema for the Easyship multi-carrier shipping API. Easyship provides e-commerce businesses with access to 250+ couriers for rate comparison, label generation, shipment management, pickup scheduling, returns, duties and tax calculation, and real-time tracking. The schema below translates the REST API surface into GraphQL types, queries, and mutations.

The source REST API is documented at https://developers.easyship.com/

## Schema Source

Conceptual schema derived from:
- Easyship developer documentation: https://developers.easyship.com/docs
- Easyship API reference: https://developers.easyship.com/reference
- Easyship LLMs.txt: https://developers.easyship.com/llms.txt

## Types Summary

| Type | Description |
|------|-------------|
| Shipment | A shipment record including origin, destination, items, and carrier assignment |
| ShipmentDetails | Extended metadata for a shipment including platform and billing references |
| ShipmentStatus | Current status code and description for a shipment lifecycle |
| ShipmentItem | A single line item within a shipment |
| ItemDetails | Product description and category information for an item |
| ItemSKU | Stock keeping unit identifier for a product |
| ItemValue | Declared monetary value of an item for customs and insurance |
| ItemWeight | Weight measurement of an item |
| ItemDimension | Physical dimensions (length, width, height) of an item |
| ShipperAddress | Origin address for a shipment |
| DestinationAddress | Delivery destination address for a shipment |
| RecipientName | Full name of the shipment recipient |
| RecipientPhone | Phone contact for the recipient |
| RecipientEmail | Email contact for the recipient |
| Carrier | A courier integrated with Easyship |
| CarrierDetails | Extended information about a carrier including service zones and features |
| CourierService | A specific service offering from a carrier |
| CourierRate | Quoted rate for a courier service for a given shipment |
| DeliveryTime | Estimated transit and delivery time for a courier service |
| ShippingFee | Base shipping cost for a courier service |
| InsuranceFee | Optional insurance cost for a shipment |
| FuelFee | Fuel surcharge applied by a carrier |
| PickupFee | Fee for scheduled courier pickup |
| DutyFee | Import duty charge for cross-border shipments |
| TaxFee | Tax charge (VAT/GST) for cross-border shipments |
| Rate | Aggregated rate object combining all fees for a courier option |
| RateInfo | Metadata about a rate quote including validity and conditions |
| RateCarrier | Carrier details embedded within a rate response |
| HandledBy | Indicates whether duties/taxes are handled by shipper or recipient (DDP/DDU) |
| Coverage | Insurance coverage type and limits |
| InsuranceOption | Available insurance product for a shipment |
| InsuredValue | Declared insured value for a shipment |
| DeclaredValue | Customs-declared value for a shipment |
| Customs | Customs declaration record for an international shipment |
| CustomsDetails | Detailed customs item-level declaration |
| CustomsDeclaration | Complete customs form data including incoterms |
| HSTariffCode | Harmonized System tariff classification code |
| CustomsType | Type of customs declaration (gift, sale, return, sample) |
| ReturnShipment | A return shipment record linked to an original forward shipment |
| ReturnLabel | Label generated for a return shipment |
| ReturnStatus | Current status of a return shipment |
| Label | Shipping label generated for a shipment |
| LabelURL | URL pointing to a generated label document (PDF or PNG) |
| TrackingNumber | Carrier-assigned tracking identifier |
| TrackingStatus | Current tracking status for a shipment |
| TrackingEvent | A single event in the tracking history of a shipment |
| TrackingURL | Public-facing tracking URL for a shipment |
| PickupRequest | A scheduled pickup request submitted to a carrier |
| PickupDetails | Details of a scheduled pickup including address and contact |
| PickupDate | Date on which a pickup is scheduled |
| PickupWindow | Time window within a pickup date when a carrier will collect |
| DropoffPoint | A carrier dropoff location where shipments can be self-delivered |
| Box | A box or packaging unit used for a shipment |
| BoxDimension | Physical dimensions of a box |
| APIKey | An API key credential for authenticating to the Easyship API |
| Token | OAuth 2.0 bearer token used to authorize API requests |
| Webhook | A webhook subscription for receiving Easyship event notifications |

## Queries

- `shipment(id: ID!)` — Fetch a single shipment by ID
- `shipments(status: ShipmentStatusEnum, limit: Int, offset: Int)` — List shipments with optional filters
- `rates(input: RateInput!)` — Get available courier rates for a shipment specification
- `carrier(id: ID!)` — Fetch a single carrier by ID
- `carriers` — List all carriers available in the account
- `label(shipmentId: ID!)` — Retrieve label for a shipment
- `tracking(trackingNumber: String!)` — Get tracking status and events
- `pickupRequest(id: ID!)` — Fetch a pickup request by ID
- `dropoffPoints(countryCode: String!, postalCode: String)` — List carrier dropoff points near a location
- `box(id: ID!)` — Fetch a box configuration by ID
- `boxes` — List all saved box configurations
- `returnShipment(id: ID!)` — Fetch a return shipment by ID
- `webhook(id: ID!)` — Fetch a webhook subscription by ID
- `webhooks` — List all webhook subscriptions

## Mutations

- `createShipment(input: CreateShipmentInput!)` — Create a new shipment record
- `updateShipment(id: ID!, input: UpdateShipmentInput!)` — Update shipment details
- `cancelShipment(id: ID!)` — Cancel a shipment
- `buyLabel(shipmentId: ID!, courierId: ID!)` — Purchase a label for a shipment with a selected courier
- `createPickupRequest(input: CreatePickupInput!)` — Schedule a courier pickup
- `cancelPickupRequest(id: ID!)` — Cancel a scheduled pickup
- `createReturnShipment(input: CreateReturnInput!)` — Initiate a return shipment
- `createBox(input: BoxInput!)` — Save a new box configuration
- `updateBox(id: ID!, input: BoxInput!)` — Update a box configuration
- `deleteBox(id: ID!)` — Delete a box configuration
- `createWebhook(input: WebhookInput!)` — Create a new webhook subscription
- `updateWebhook(id: ID!, input: WebhookInput!)` — Update a webhook subscription
- `deleteWebhook(id: ID!)` — Remove a webhook subscription

## Authentication

The Easyship API uses OAuth 2.0 bearer tokens. Clients obtain a token by exchanging API credentials and include it in the `Authorization: Bearer <token>` header on all requests.

## Notes

- All monetary values use `Float` with a `currency` field (ISO 4217 code, e.g., `USD`, `HKD`)
- Weights use grams by default; dimensions use centimeters
- Cross-border shipments require a `Customs` object with per-item `CustomsDetails`
- The `HandledBy` type encodes DDP (Delivery Duty Paid) vs DDU (Delivery Duty Unpaid) incoterms
- Tracking events are ordered chronologically, newest last
