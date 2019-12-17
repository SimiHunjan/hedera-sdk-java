# Errors



| **`Error`**  | **`Description`** |
| :--- | :--- |
| `INVALID_TOPIC_ID` | `The Topic ID specified is not in the system.` |
| `TOPIC_DELETED` | The Topic has been deleted |
| `INVALID_TOPIC_EXPIRATION_TIME` |  |
| `INVALID_TOPIC_ADMIN_KEY` |  |
| `INVALID_TOPIC_SUBMIT_KEY` |  |
| `UNAUTHORIZED` | An attempted operation was not authorized \(ie - a deleteTopic for a topic with no adminKey\) |
| `INVALID_TOPIC_MESSAGE` | A ConsensusService message is empty |
| `INVALID_AUTORENEW_ACCOUNT` | The autoRenewAccount specified is not a valid, active account. |
| `AUTORENEW_ACCOUNT_NOT_ALLOWED` | An admin key was not specified on the topic, so there must not be an autorenew account. |
| `AUTORENEW_ACCOUNT_SIGNATURE_MISSING` | The autoRenewAccount didn't sign the transaction. |

