..
   Copyright (c) 2024 Digital Asset (Switzerland) GmbH and/or its affiliates. All rights reserved.
..
   SPDX-License-Identifier: Apache-2.0



.. NOTE: add your upcoming release notes below this line. They are included in the `release_notes.rst`.

.. release-notes:: Upcoming

  - Participant

    - Increase default retention parameters of the `session encryption keys cache <https://docs.digitalasset.com/operate/3.4/howtos/optimize/session_keys.html#configure-session-keys>`__.
      Most notably, increase the lifetime of session encryption keys from 10 minutes to 1 hour,
      to improve performance and reduce (KMS) costs throughout the network.
      This change has no practical security implication for participants that are not using an external KMS:
      in this case the main (asymmetric) encryption keys are usually already available in memory (in addition to being stored inside the participant database).
      We encourage operators of KMS-enabled participants to review the updated sections on KMS usage for :ref:`validator participants <validator-kms-config>` and :ref:`SV participants <sv-kms-participant>` for more pointers about the security impact of session key caching and ways to tweak the relevant parameters to individual needs.

   - SV app

     - Improve the automation for converting featured app activity
       markers to handle batches of markers for nodes that have not
       vetted the same version of the amulet package.

  - Wallet UI

    - Introduced a new ``/development-fund`` panel providing a complete UI for managing Development Fund allocations.

    - The panel includes:

      - Display of total available Development Fund balance
      - Allocation form for Development Fund coupons (Development Fund Manager only)
      - Unclaimed allocations table with withdrawal support
      - Coupon history with lifecycle event tracking (claimed, withdrawn, rejected, expired)

    - Role-based behavior is enforced:

      - Simple Users: read-only access to fund total
      - Current Development Fund Manager: full allocation and withdrawal capabilities
      - Former Development Fund Manager: can manage and view allocations created under their tenure, but cannot create new ones

