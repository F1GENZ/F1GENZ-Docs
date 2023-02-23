---
sidebar_position: 2
---

# Tồn kho

### For danh sách toàn bộ cửa hàng

```jsx
{%- for address in shop.addresses -%}
	id: {{ address.id }},
  	name: {{ address.location_name }},
	province: {{ address.province_name }},
	district: {{ address.district_name }},
	ward: {{ address.ward_name }},
	street: {{ address.street }},
{%- endfor -%}
```

### Check cửa hàng còn hàng với Ajax

```jsx title="JSON"
`/inventory_location.js?variant_id={variant.id}&quantity=1`;
```

### Check cửa hàng còn hàng với selected_variant

```jsx
{% layout none %}
{
 "variantLocations": [
   {%- for loc in product.selected_variant.locations -%}
    {
     "LocationId": "{{ loc.id }}",
     "LocationName": "{{ shop.addresses[loc.id].location_name }}",
     "LocationAddress": "{{ shop.addresses[loc.id].summary | remove: ', Vietnam' | remove: ', vietnam' }}",
     "Quantity": "{{loc.quantity}}"
    }{% unless forloop.last %},{% endunless %}
   {%- endfor -%}
 ]
}
```
