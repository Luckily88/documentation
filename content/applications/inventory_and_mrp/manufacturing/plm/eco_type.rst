.. _plm/eco/eco-type:

.. |BOM| replace:: :abbr:`BoM (Bill of Materials)`
.. |ECO| replace:: :abbr:`ECO (Engineering Change Order)`
.. |ECOs| replace:: :abbr:`ECOs (Engineering Change Orders)`

========
ECO type
========

Organize engineering change orders (ECOs) into a *ECO type* project and create custom stages to
track the progress of changes within a structured Gantt view project pipeline. This categorization
ensures that collaborators and stakeholders only view and assist with relevant |BOM| improvements.

Create ECO type
===============

To access and manage ECO types, navigate to :menuselection:`PLM app --> Configuration --> ECO
Types`.

Create a new ECO type by clicking :guilabel:`New`. On the new :guilabel:`ECO Types` form, fill in
the following information:

- :guilabel:`Name`: the name of the |ECO| and will organize all of the |ECOs| of this *type* in a
  project.
- :guilabel:`Email Alias`: an optional field. If filled, emails submitted to this email address will
  automatically generate |ECOs| in the left-most stage of this |ECO| type.

.. example::
   The `Formulation change` |ECO| type is used to organize and track related |ECOs| in a single
   project. Configuring the :guilabel:`Email Alias` field generates |ECOs| in the `Formulation
   change` project sent to the email address, `pawlish-change@pawlished-glam.odoo.com`.

   .. image:: eco_type/create-eco-type.png
      :align: center
      :alt: Example of an ECO type.

Edit ECO type
=============

Modify existing |ECO| type names and email aliases by clicking by navigating to the
:menuselection:`PLM app --> Configuration --> ECO Types` page. There, click on the desired on the
desired |ECO| type from the list. On the form for each |ECO| type, edit the :guilabel:`Name` and
:guilabel:`Email Alias` fields.

.. _plm/eco/stage-config:

Stage configuration
===================

*Stages* in each |ECO| type help to organize and track the progress of |ECOs|. Additionally,
approvers can be configured on each stage to enforce reviews on changes and prevent errors on the
production |BOM|.

For best practice, at there is at least one *verification* stage, which is a stage with a required
approver, and one *closing* stage, which stores |ECOs| that have been either canceled or approved
for use as the next production |BOM|.

Verification stage
------------------

Click an ECO type from :menuselection:`PLM app --> Overview` to open a kanban view of |ECOs| of this
type.

To configure a verification stage, hover over the intended stage, and select the :guilabel:`⚙️
(gear)` icon. Then, click :guilabel:`Edit` to open a pop-up window.

Configure the verification stage in the edit stage pop-up window, by checking the box for
:guilabel:`Allow to apply changes`.

Add an approver in the :guilabel:`Approvers` section by clicking :guilabel:`Add a line` and
specifying the :guilabel:`Role` of the reviewer, their :guilabel:`User`, and :guilabel:`Approval
Type`. Ensure at least one approver is configured with the :guilabel:`Approval Type`, :guilabel:`Is
required to approve`.

The approver listed will be automatically notified when |ECOs| are dropped in the stage specified in
the pop-up. Once finished, select the :guilabel:`Save & Close` button.

.. example::
   In the |ECO| type `New Product Introduction`, the verification stage `Validated` is configured by
   clicking :guilabel:`⚙️ (gear)` icon and selecting :guilabel:`Edit`. Doing so opens the
   :guilabel:`Edit: Validated` pop-up window.

   By adding the `Engineering manager` as an approver, only |ECOs| approved by this user can proceed
   to the next stage and have the changes applied on the production |BOM|.

   Additionally, check the :guilabel:`Allow to apply changes` option ensure proper behavior.

   .. image:: eco_type/verification-stage.png
      :align: center
      :alt: Show "Allow to apply changes" option is checked.

Closing stage
-------------

To configure a closing stage, hover over the closing stage, and select the corresponding
:guilabel:`⚙️ (gear)` icon to open the edit stage pop-up window. Ensure that the :guilabel:`Folded
in kanban view`, :guilabel:`Allow to apply changes`, and :guilabel:`Final Stage` options are
checked.

.. example::
   The closing stage, `Effective` is configured by checking the :guilabel:`Folded in kanban view`,
   :guilabel:`Allow to apply changes`, and :guilabel:`Final Stage` options

.. image:: eco_type/closing-stage.png
   :align: center
   :alt: Show configurations of the closing stage.

