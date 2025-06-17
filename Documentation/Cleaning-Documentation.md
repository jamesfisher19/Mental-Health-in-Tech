| Step # | Action Taken                                                         | Column(s) Affected             | Reason                                                                              |
| ------ | -------------------------------------------------------------------- | ------------------------------ | ----------------------------------------------------------------------------------- |
| 1      | Remove timestamp column                                              | Timestamp                      | The time of the response submission is irrelevant                                   |
| 2      | Change negative ge (-29) to positive (29)                            | Age                            | Safely assuming this was a typo on surveyor's part                                  |
| 3      | Delete outlier rows by age                                           | Age                            | Ages are -1, -1726, 5, 8, 11, 329, & 99999999999 (outliers). Removed ages under 18. |
| 4      | Find & Replace all rows containing "female", replaced with "FEMALE"  | Gender                         | Standardize 'Gender' column                                                         |
| 5      | Find & Replace all rows beginning with "male", replaced with "MALE"  | Gender                         | Standardize 'Gender' column                                                         |
| 6      | Filter all rows with Male typos and replace with "MALE"              | Gender                         | Standardize 'Gender' column                                                         |
| 7      | Filter all rows with Female typos and replace with "FEMALE"          | Gender                         | Standardize 'Gender' column                                                         |
| 8      | Filter all rows alluding to non-binary and replace with "NON-BINARY" | Gender                         | Standardize 'Gender' column                                                         |
| 9      | Delete joke responses (1x)                                           | Gender                         | Standardize 'Gender' column                                                         |
| 10     | Remove duplicates (11x)                                              | All                            | Remove duplicate submissions                                                        |
| 11     | Remove blank rows                                                    | All (based on 'self-employed') | Remove blank rows                                                                   |
- Created new column called `stigma` representing whether a stigma is perceived based on columns `mental_health_consequences` and `obs_consequences`.
- Created calculated field to get the percentage of respondents that perceived a stigma in mental health
