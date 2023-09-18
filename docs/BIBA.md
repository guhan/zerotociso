# Biba Model
The Biba Model is a computer security model that focuses on data integrity. It is named after its creator, Kenneth J. Biba, who introduced it in the 1970s. The Biba Model is used to establish and enforce access control policies that prevent unauthorized users or processes from making changes to data in a way that would compromise its integrity.

The key principles of the Biba Model are based on the concept of maintaining data integrity through controlled access. 

Addresses integrity more than confidentiality
- Better for commercial vs military
- Prevent modificiton of objects by unauthorized subjects
- Prevent unauthorized modification of objects by authorized subjects
- Protect internal and external object consistency
- Does not address access control no way to assign or change a subjects classification level

## Difference from Bell-LaPadula**
- Simple Security Property: subject may not read informatino at a lower sensitivity level (no read down)
- Star Secuirty Property: subject may not write information to a higher sensitivity level (no write up)


## The Simple Integrity Property (No Read Down, No Write Up):
- A subject (user, process, or entity) with a given integrity level can read data at or below its own integrity level. This is known as the "No Read Down" rule.
- A subject with a given integrity level can write (modify) data at or above its own integrity level. This is known as the "No Write Up" rule.

These principles ensure that information flows in a way that prevents lower-integrity subjects from corrupting or contaminating higher-integrity data. The Biba Model enforces a strict hierarchy of integrity levels, where data is classified according to its sensitivity or importance.

## Integrity levels

- **High Integrity (HI)**: This level is reserved for the most sensitive and critical data. Subjects with high integrity clearance can only write data at the high integrity level and can read data at the high or low integrity levels.
- **Low Integrity (LI)**: This level represents less sensitive data. Subjects with low integrity clearance can write data at the low integrity level and can read data at the low integrity level or unclassified (unrestricted) data.
- **Unclassified (U)**: This is the lowest integrity level and typically represents data that is not sensitive or restricted in any way. Subjects with any integrity level can read unclassified data.
