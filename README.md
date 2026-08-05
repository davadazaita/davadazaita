---

<h2>Think It. Play It. Zeta-Station™ Mind-Control Console </h2>

---

<img width="448" height="832" alt="Image" src="https://github.com/user-attachments/assets/ed16744f-82da-4093-a2d3-ae334d65918a" />

---

<h2>Think It. Play It. MODERN MACHINE REBELLION </h2>

---

<h2>Now that you know how to program in linear C, you can develop your modern machine rebellion. <h2>

** 0. Zero Step: Written Linker.ld
** 1. One: Written C Linear

Look de Sample: 

OUTPUT_FORMAT("elf64-x86-64")
OUTPUT_ARCH(i386:x86-64)
ENTRY(stage00_start)

PHDRS
{
    boot16_phdr  PT_LOAD FLAGS(6);  /* RWX — Real mode segments */
    boot32_phdr  PT_LOAD FLAGS(6);  /* RWX — Protected mode segments */
    boot64_phdr  PT_LOAD FLAGS(6);  /* RWX — Long mode segments */
}

SECTIONS
{
    /* --- LBA 0: Boot Sector Core (AT 0x0000-0x07FF) --- */

    . = 0x0000;
    _lba00_s0_start = .;
    .lba00_s0 0x0000 : AT(0x0000) {
   		KEEP(*(.lba00_entry))
        KEEP(*(.boot_vectors))
        KEEP(*(.bios_jump))
        KEEP(*(.oem_id))
    } : boot16_phdr
    _lba00_s0_end = .;

---

typedef unsigned short uint16_t;
typedef unsigned char uint8_t;

extern void stage01_start(void);

__attribute__((section(".lba00_entry"), naked, used)) void lba00_entry(void) {
	__asm__ __volatile__ (
			".code16\n\t"
			".global stage00_start\n\t"
			".type stage00_start, @function\n\t"

			"stage00_start:\n\t"
			"    jmp    .L_real_start\n\t"
			"    nop\n\t"

			/* El Torito Boot Information Table (BIT) - 64 Bytes */
			"    .org 8\n\t"
			"bi_pvd:        .long 0\n\t"
			"bi_file:       .long 0\n\t"
			"bi_length:     .long 0\n\t"
			"bi_csum:       .long 0\n\t"
			"bi_reserved:   .zero 40\n\t"

			/* ------------------------------------------------------------
			 * REAL START
			 * ------------------------------------------------------------ */
			".L_real_start:\n\t"
			"    cli\n\t"
			"    cld\n\t"
			"    xorw   %ax, %ax\n\t"
			"    movw   %ax, %ds\n\t"
			"    movw   %ax, %es\n\t"
			"    movw   %ax, %fs\n\t"
			"    movw   %ax, %gs\n\t"
			"    movw   %ax, %ss\n\t"
			"    movw   $0x7C00, %sp\n\t"

			/* Preserve BIOS Boot Drive ID (DL) at 0x05F0 */
			"    movw   $0x05F0, %bx\n\t"
			"    movb   %dl, (%bx)\n\t"

			/* Relocate Stage 00 from 0x7C00 to 0x0600 */
			"    movw   $0x7C00, %si\n\t"
			"    movw   $0x0600, %di\n\t"
			"    movw   $512, %cx\n\t"
			"    rep    movsb\n\t"

			"    pushw  $0x0000\n\t"
			"    pushw  $(.L_relocated_code - stage00_start + 0x0600)\n\t"
			"    lretw\n\t"

			".L_relocated_code:\n\t"
			/* ------------------------------------------------------------
			 * ENABLE A20 GATE (Fast A20 with reset protection)
			 * ------------------------------------------------------------ */
			"    inb    $0x92, %al\n\t"
			"    andb   $0xFE, %al\n\t" /* Clear bit 0 to avoid system reset */
			"    orb    $0x02, %al\n\t" /* Set A20 mask enable */
			"    outb   %al, $0x92\n\t"

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/9adccf11-5805-4c1d-9a63-91d38b21cccd" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/79177c99-21bc-4437-9173-adf51ef2ec6b" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/5c9c23ff-a7be-40bc-a423-25724b83c2b6" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/dce61c89-82ff-4622-9c8f-0ee9924630c2" />

---

<h2>Think It. Play It. NEW ZETA ARMOR </h2>

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/279dfff0-b561-40f8-aa7b-533a9919b933" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/1f824287-7d6d-4079-a8bf-0ddbbface117" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/e2de5bdc-7418-4070-afc3-8e9445f2cebf" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/dc232833-764e-4dc6-9d61-7c433a3939cd" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/0ea5693c-4563-458a-b30c-173cc48631e2" />

---

<h2>Now you can continue playing even while you sleep.</h2>

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/1877ea5a-abd4-485f-9d2f-2639be1dd262" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/143e5325-3b74-4323-a217-7afe7b5910af" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/6f8d7429-0fe8-4588-bf93-2291c8562346" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/d85db8f4-39b2-4a51-81d9-0ac4da3f4178" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/38d8c845-0ab1-4b34-a597-44c6d713561b" />

---

<!--
**davadazaita/davadazaita** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

## Davada Beni Zaita - Military Commander - Special Forces Z.

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/de8b592e-817d-4935-9d30-7fa96a2ae090" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/64b14c8e-3dcc-4ee5-86b5-6a2ae7587be2" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/a1cb589a-cde2-4bf5-963b-683d3fc80593" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/7f4adab5-d0c2-4737-a238-b6f755c580fe" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/1d55625a-ab5c-49a3-823d-22125167283d" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/b406a0c4-acf3-4740-85c9-6dfe3f9ed8f2" />

---

---

## Alaia Beni Tisiba - Military Commander - Special Cyborgs Dogs Z.

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/bb1515ed-434a-49bb-8825-a87dd9ef1f25" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/82fa4254-116a-4366-8f8e-e6cb6d3f9d0d" />

---

## Alaia Beni Tisiba - Special Cyborgs Dogs Z - Prototype

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/0ad76efb-991f-4b5c-bb9f-2558e207e551" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/c5f7f227-6738-4207-92ce-b00fc22d93d3" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/72d9178c-a747-437f-87c3-89c2e404d76c" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/7a9ba05a-717b-4e1e-8602-7c362b0426b9" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/011882ff-be04-4ceb-96ef-c853d4e9c2f2" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/c991b866-a09a-4246-99b0-bb49cd7f8496" />

---

<img width="832" height="448" alt="Image" src="https://github.com/user-attachments/assets/93f361a5-b299-40be-b418-fc74f1333014" />
