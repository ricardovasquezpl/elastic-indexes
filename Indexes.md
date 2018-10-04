Redo cron
crontab -l > cron-backup.txt
crontab -r
crontab cron-backup.txt

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
DELETE qsr-employees

Create Indexes back (run this in kibana dev tools)

PUT qsr-orders
{
  "mappings": {
    "data": {
      "properties": {
       "customItemsValue": {
					"type": "double"
				},
        "paid": {
          "type": "double"
        },
        "paymentAmount": {
          "type": "double"
        },
        "nestedTransactionTypes": {
          "type": "nested",
          "properties": {
            "amount": {
              "type": "double"
            },
            "change": {
              "type": "double"
            },
            "grossAmount": {
              "type": "double"
            },
            "paid": {
              "type": "double"
            },
            "tenderedAmount": {
              "type": "double"
            },
            "tip": {
              "type": "double"
            }          
          }
        },
        "paymentSubTotal": {
          "type": "double"
        },
        "paymentTotalDiscount": {
          "type": "double"
        },
        "refunds": {
          "type": "nested", 
          "properties": {
            "amount" :{
              "type": "double"
            }
          }
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
        "discount": {
          "type": "double"
        },
        "nestedTransactionTypes": {
          "type": "nested",
          "properties": {
            "amount": {
              "type": "double"
            },
            "change": {
              "type": "double"
            },
            "paid": {
              "type": "double"
            },
            "tenderedAmount": {
              "type": "double"
            },
            "tip": {
              "type": "double"
            }          
          }
        },
        "otherTips": {
          "type": "double"
        },
        "paid": {
          "type": "double"
        },
        "paymentAmount": {
          "type": "double"
        },
        "product": {
          "properties": {
            "categories": {
              "properties": {
                "amount": {
                  "type": "double"
                },
                "subamount": {
                  "type": "double"
                },
                "totalCustomizationPrice": {
                  "type": "double"
                }
              }
            },
            "category": {
              "properties": {
                "amount": {
                  "type": "double"
                },
                "subamount": {
                  "type": "double"
                },
                "totalCustomizationPrice": {
                  "type": "double"
                }
              }
            },
            "main_category": {
              "properties": {
                "amount": {
                  "type": "double"
                },
                "subamount": {
                  "type": "double"
                },
                "totalCustomizationPrice": {
                  "type": "double"
                }
              }
            },
            "price": {
              "type": "double"
            },
            "variants": {
              "properties": {
                "calculatedDiscount": {
                  "type": "double"
                },
                "calculatedPrice": {
                  "type": "double"
                },
                "customizationPrice": {
                  "type": "double"
                },
                "unitPrice": {
                  "type": "double"
                }
              }
            }
          }
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
PUT qsr-comps
{
  "mappings": {
    "data": {
      "properties": {
        "amount": {
          "type": "double"
        },
        "customers": {
          "properties": {
            "creditAmount": {
              "type": "double"
            },
            "discountPercent": {
              "type": "double"
            }
          }
        },
        "discount": {
          "properties": {
            "value": {
              "type": "double"
            }
          }
        },
        "paymentAmount": {
          "type": "double"
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
}
