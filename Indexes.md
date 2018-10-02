Clean data from Elasticsearch (run this in kibana dev tools)
DELETE qsr-orders
DELETE qsr-orders-products
DELETE qsr-orders-variants
DELETE qsr-labor-sales
DELETE qsr-comps
DELETE qsr-shifts
DELETE qsr-menus
DELETE qsr-products
DELETE qsr-transactiontypes
DELETE qsr-roles
DELETE qsr-users
DELETE qsr-productcategories
DELETE qsr-jobtypes
DELETE qsr-discounts
DELETE qsr-locations
DELETE qsr-workinghours
DELETE qsr-labor-hours

Create Indexes back (run this in kibana dev tools)

PUT qsr-orders
{
  "mappings": {
    "data": {
      "properties": {
        "paid": {
            "type": "double"
        },
        "paymentAmount": {
            "type": "double"
        },
        "nestedTransactionTypes": {
          "type": "nested"
        },
        "paymentSubTotal": {
           "type": "double"
        },
        "paymentTotalDiscount": {
          "type": "double"
        },
        "serviceCharges": {
            "type": "double"
         },
        "subTotal": {
          "type": "double"
        },
        "tips": {
          "type": "double"
        },
        "totalDiscount": {
          "type": "double"
        },
        "totalPrice": {
          "type": "double"
        },
        "totalServiceCharge": {
          "type": "double"
        },
        "totalTax": {
          "type": "double"
        },
        "customItemsValue": {
          "type": "double"
        }
      }
    }
  }
}
PUT qsr-orders-products
{
  "mappings": {
    "data": {
      "properties": {
        "paid": {
          "type": "double"
        },
        "tips": {
          "type": "double"
        },
        "discount": {
          "type": "double"
        },
        "total": {
          "type": "double"
        }
      }
    }
  }
}
PUT qsr-orders-variants
{
  "mappings": {
    "data": {
      "properties": {
        "discount": {
          "type": "double"
        },
        "paid": {
          "type": "double"
        },
        "tips": {
          "type": "double"
        },
        "total": {
          "type": "double"
        }
      }
    }
  }
}
PUT qsr-labor-sales
{
  "mappings": {
    "data": {
      "properties": {
        "jobtypes": {
          "type": "nested"
        }
      }
    }
  }
}
GET qsr-comps
PUT qsr-comps
{
  "mappings": {
    "data": {
      "properties": {
        "amount": {
          "type": "float"
        },
        "customers": {
          "properties": {
            "creditAmount": {
              "type": "float"
            },
            "discountPercent": {
              "type": "float"
            }
          }
        },
        "discount": {
          "properties": {
            "value": {
              "type": "float"
            }
          }
        },
        "paymentAmount": {
          "type": "float"
        }
      }
    }
  }
}
PUT qsr-shifts
PUT qsr-menus
PUT qsr-products
PUT qsr-transactiontypes
PUT qsr-roles
PUT qsr-users
PUT qsr-productcategories
PUT qsr-jobtypes
PUT qsr-discounts
PUT qsr-locations
{
  "mappings": {
    "data": {
      "properties": {
        "coordinates": {
          "type": "geo_point"
        }
      }
    }
  }
}
PUT qsr-workinghours
PUT qsr-labor-hours
{
  "mappings": {
    "data": {
      "properties": {
        "jobtypes": {
          "type": "nested"
        },
        "alljobtypes": {
          "type": "nested"
        }
      }
    }
  }
