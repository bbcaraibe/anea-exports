# H59 wristbands — defective batch (HRV / SpO2 not working + constant disconnections)

**To:** Supplier
**Subject:** Return of 27 H59 units — HRV and SpO2 measurements non-functional and repeated Bluetooth disconnections

---

Hello,

After testing the H59 units from this batch, we are returning **27 pieces** for the
following reasons. These are **hardware/firmware faults on the units themselves**,
not an application problem — our app correctly sends the SpO2 and HRV measurement
commands and reads the responses; the bands do not deliver valid data.

## 1. SpO2 (blood oxygen) does not work

- At connection, each band reports its own **feature flags** (a "supported features"
  map). On these units, the **blood-oxygen capability is either reported as not
  supported, or the sensor returns no valid value**.
- A SpO2 reading requires a working **red-LED optical (PPG) sensor**. On this batch
  the band sends only a raw signal but **never a plausible result** (the valid
  physiological range is 50–100%). Our app refuses to display a fabricated number,
  so it correctly shows nothing.

## 2. HRV (heart-rate variability) does not work

- HRV is computed from a **clean, continuous pulse signal**. On these units the HRV
  command returns **empty**, so no HRV value can be produced.

## 3. Constant Bluetooth disconnections

- The H59 protocol requires a **mandatory periodic keep-alive**. On this batch the
  **firmware drops the connection** even when the phone side behaves correctly.
- This is compounded by typical low-grade hardware issues: **weak/aging battery**,
  **low-quality BLE chip** (poor range and stability), and link loss in background.

## Conclusion

These 27 units have **limited/defective sensors and unstable firmware**. The
SpO2 and HRV functions advertised for the H59 are not usable on this batch, and the
constant disconnections make normal use impossible.

We are therefore returning the **27 affected units**. (The remaining units cannot be
returned as we no longer have their original boxes.)

A short demonstration video is available showing, on one unit:
1. successful connection,
2. SpO2 measurement → no value / failure,
3. HRV measurement → no value,
4. spontaneous disconnection during use.

We request a resolution (replacement with conforming units or refund) for the
returned items.

Best regards,
