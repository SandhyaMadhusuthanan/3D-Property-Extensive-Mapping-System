# Problem Statement

## 1. Land Records Are Still Fundamentally 2D

Even with digitization efforts like ULPIN and DILRMP, the underlying data model is a **flat survey map**. A land parcel is represented as a polygon with an owner's name attached. This works for open land, but breaks down the moment something is *built* on that land.

## 2. Vertical Ownership Has No Formal Address

Consider a 6-floor apartment building on a single plot:

- The **land** has one ULPIN.
- But there are 6 floors, each with multiple flats, each independently owned or rented.
- There are parking bays — some allotted to specific units, some for visitors, some for EV charging.
- There may be a terrace, a basement, and unbuilt "air rights" above the roof.

None of these sub-units have a standard, government-recognized identifier. Ownership of a flat is usually proven only through a private sale deed — not through a searchable, linked land record.

## 3. Joint Ownership Is Hard to Track

Multiple people often buy land together (e.g., family members or business partners) and hold **undivided shares** in a single ULPIN. Today there is no clean digital way to:

- See each member's exact percentage share.
- See who joined later via a share transfer, and from whom.
- See who has since sold out entirely and is no longer a shareholder.

This makes disputes over inheritance, resale, and shared land common and hard to resolve.

## 4. Parking and Common Areas Are Undocumented

Parking bays attached to apartments and shops are rarely individually recorded. Disputes over "whose parking spot is this" are common in Indian residential complexes because there is no sub-parcel-level record — just a verbal or society-level allocation.

## 5. Buyers Can't Verify What They're Actually Buying

A prospective buyer looking at a plot in a large layout often struggles to:

- Physically locate their exact plot among dozens of look-alike plots.
- Understand how nearby government projects (metro lines, roads) might affect the land's future value.
- See a realistic price trend before committing to a purchase.

## 6. No Visual, Explorable Record Exists

Government officials and citizens alike currently rely on paper documents, PDFs, or basic 2D GIS viewers. There is no interactive, 3D, click-to-explore representation of a property that ties ownership, structure, and location together in one place.

## Summary

The core problem is a **dimensional gap**: land records track *where* a parcel is, but not *what exists on it, layer by layer, and who owns each layer*. This project addresses that gap directly.
