{{ objname | escape | underline }}

.. currentmodule:: {{ module }}

.. autoclass:: {{ objname }}
   :members:

   {% block methods %}
   {% if methods %}
   .. rubric:: {{ _('Methods') }}

   .. autosummary::
      :nosignatures:
   {% for item in methods %}
   {% if item != "__init__" and item not in inherited_members %}
      ~{{ name }}.{{ item }}
   {% endif %}
   {% endfor %}
   {% endif %}
   {% endblock %}
