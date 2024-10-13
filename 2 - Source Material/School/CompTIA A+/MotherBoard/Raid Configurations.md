

Tags: [[raid]] [[school]] [[IT]] [[CompTIA_A+]] [[hardware]] [[Cyber Security]] 
Date: 2024-10-12 11:30

---

## Source: 
[Professor Messer](https://www.youtube.com/watch?v=A_UXW9lUCxY&t=225s)

---

## Summary:


---

## Detailed Notes:
Sure! Here's a concise explanation of RAID for your CompTIA A+ source notes:

---

### RAID (Redundant Array of Independent Disks)

RAID is a technology that combines multiple hard drives into a single unit to achieve redundancy, performance, or both. It is used in servers and workstations for data protection and improved disk performance. There are several levels of RAID, each offering different benefits:

1. **RAID 0 (Striping)**:
   - **Purpose**: Improves performance.
   - **How it works**: Data is split (striped) across multiple disks.
   - **Benefits**: Faster read/write speeds as data is accessed from multiple disks simultaneously.
   - **Drawbacks**: No redundancy—if one disk fails, all data is lost.
![[Screenshot 2024-10-12 114100.png]]



2. **RAID 1 (Mirroring)**:
   - **Purpose**: Provides redundancy by duplicating data.
   - **How it works**: Data is mirrored, or copied, onto two or more disks.
   - **Benefits**: High fault tolerance—if one disk fails, the other contains a complete copy.
   - **Drawbacks**: Slower write performance and reduced storage capacity (since data is duplicated).

![[Screenshot 2024-10-12 114120.png]]

3. **RAID 5 (Striping with Parity)**:
   - **Purpose**: Offers a balance between performance and redundancy.
   - **How it works**: Data is striped across multiple disks with parity information distributed across all drives. Parity allows recovery if a single drive fails.
   - **Benefits**: Efficient use of storage space and fault tolerance.
   - **Drawbacks**: Slightly slower write performance due to parity calculations.
![[Screenshot 2024-10-12 114331.png]]




4. **RAID 6 (Striping with Double Parity)**:
   - **Purpose**: Similar to RAID 5 but with added redundancy.
   - **How it works**: Data is striped across multiple disks with two sets of parity data, allowing for recovery from the failure of two disks.
   - **Benefits**: Higher fault tolerance than RAID 5.
   - **Drawbacks**: Slower write performance than RAID 5 due to the overhead of calculating two parity blocks.

5. **RAID 10 (1+0)**:
   - **Purpose**: Combines the benefits of RAID 1 and RAID 0.
   - **How it works**: Data is both striped and mirrored—data is striped across pairs of mirrored disks.
   - **Benefits**: High performance and fault tolerance.
   - **Drawbacks**: High cost due to needing twice the number of disks (like RAID 1).
![[raid-levels-explained.png]]


---

Let me know if you need more detailed information or any clarifications!
  

---

---


