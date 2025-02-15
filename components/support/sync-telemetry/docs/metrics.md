<!-- AUTOGENERATED BY glean_parser v6.1.1. DO NOT EDIT. -->

# Metrics

This document enumerates the metrics collected by this project using the [Glean SDK](https://mozilla.github.io/glean/book/index.html).
This project may depend on other projects which also collect metrics.
This means you might have to go searching through the dependency tree to get a full picture of everything collected by this project.

# Pings

- [addresses-sync](#addresses-sync)
- [bookmarks-sync](#bookmarks-sync)
- [creditcards-sync](#creditcards-sync)
- [history-sync](#history-sync)
- [logins-sync](#logins-sync)
- [sync](#sync)
- [tabs-sync](#tabs-sync)

## addresses-sync

A ping sent for every Addresses engine sync. It doesn't include the `client_id` because it reports a hashed version of the user's Firefox Account ID.


**Data reviews for this ping:**

- <https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481>

**Bugs related to this ping:**

- <https://github.com/mozilla-mobile/android-components/issues/10371>

All Glean pings contain built-in metrics in the [`ping_info`](https://mozilla.github.io/glean/book/user/pings/index.html#the-ping_info-section) and [`client_info`](https://mozilla.github.io/glean/book/user/pings/index.html#the-client_info-section) sections.

In addition to those built-in metrics, the following metrics are added to the ping:

| Name | Type | Description | Data reviews | Extras | Expiration | [Data Sensitivity](https://wiki.mozilla.org/Firefox/Data_Collection) |
| --- | --- | --- | --- | --- | --- | --- |
| addresses_sync.failure_reason |[labeled_string](https://mozilla.github.io/glean/book/user/metrics/labeled_strings.html) |Records why the addresses sync failed: either due to an authentication error, unexpected exception, or other error. The error strings are truncated and sanitized to omit PII, like URLs and file system paths.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)|<ul><li>other</li><li>unexpected</li><li>auth</li></ul>|never |2 |
| addresses_sync.finished_at |[datetime](https://mozilla.github.io/glean/book/user/metrics/datetime.html) |Records when the addresses sync finished. This includes the time to download, apply, and upload all records.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)||never |2 |
| addresses_sync.incoming |[labeled_counter](https://mozilla.github.io/glean/book/user/metrics/labeled_counters.html) |Records incoming addresses record counts. `applied` is the number of incoming records that were successfully stored or updated in the local database. `failed_to_apply` is the number of records that were ignored due to errors. `reconciled` is the number of merged records.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)|<ul><li>applied</li><li>failed_to_apply</li><li>reconciled</li></ul>|never |2 |
| addresses_sync.outgoing |[labeled_counter](https://mozilla.github.io/glean/book/user/metrics/labeled_counters.html) |Records outgoing addresses record counts. `uploaded` is the number of records that were successfully sent to the server. `failed_to_upload` is the number of records that weren't uploaded, and will be retried on the next sync.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)|<ul><li>uploaded</li><li>failed_to_upload</li></ul>|never |2 |
| addresses_sync.outgoing_batches |[counter](https://mozilla.github.io/glean/book/user/metrics/counter.html) |Records the number of batches needed to upload all outgoing records. The Sync server has a hard limit on the number of records (and request body bytes) on the number of records that can fit into a single batch, and large syncs may require multiple batches.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)||never |2 |
| addresses_sync.started_at |[datetime](https://mozilla.github.io/glean/book/user/metrics/datetime.html) |Records when the addresses sync started.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)||never |2 |
| addresses_sync.uid |[string](https://mozilla.github.io/glean/book/user/metrics/string.html) |The user's hashed Firefox Account ID.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)||never |2 |

## bookmarks-sync

A ping sent for every bookmarks sync. It doesn't include the `client_id` because it reports a hashed version of the user's Firefox Account ID.


**Data reviews for this ping:**

- <https://github.com/mozilla-mobile/android-components/pull/3092>

**Bugs related to this ping:**

- <https://github.com/mozilla-mobile/android-components/pull/3092>

All Glean pings contain built-in metrics in the [`ping_info`](https://mozilla.github.io/glean/book/user/pings/index.html#the-ping_info-section) and [`client_info`](https://mozilla.github.io/glean/book/user/pings/index.html#the-client_info-section) sections.

In addition to those built-in metrics, the following metrics are added to the ping:

| Name | Type | Description | Data reviews | Extras | Expiration | [Data Sensitivity](https://wiki.mozilla.org/Firefox/Data_Collection) |
| --- | --- | --- | --- | --- | --- | --- |
| bookmarks_sync.failure_reason |[labeled_string](https://mozilla.github.io/glean/book/user/metrics/labeled_strings.html) |Records bookmark sync failure reasons.  |[mozilla-mobile/android-components#3092](https://github.com/mozilla-mobile/android-components/pull/3092)|<ul><li>other</li><li>unexpected</li><li>auth</li></ul>|never |2 |
| bookmarks_sync.finished_at |[datetime](https://mozilla.github.io/glean/book/user/metrics/datetime.html) |Records when the bookmark sync finished.  |[mozilla-mobile/android-components#3092](https://github.com/mozilla-mobile/android-components/pull/3092)||never |2 |
| bookmarks_sync.incoming |[labeled_counter](https://mozilla.github.io/glean/book/user/metrics/labeled_counters.html) |Records incoming bookmark record counts.  |[mozilla-mobile/android-components#3092](https://github.com/mozilla-mobile/android-components/pull/3092)|<ul><li>applied</li><li>failed_to_apply</li><li>reconciled</li></ul>|never |2 |
| bookmarks_sync.outgoing |[labeled_counter](https://mozilla.github.io/glean/book/user/metrics/labeled_counters.html) |Records outgoing bookmark record counts.  |[mozilla-mobile/android-components#3092](https://github.com/mozilla-mobile/android-components/pull/3092)|<ul><li>uploaded</li><li>failed_to_upload</li></ul>|never |2 |
| bookmarks_sync.outgoing_batches |[counter](https://mozilla.github.io/glean/book/user/metrics/counter.html) |Records the number of batches needed to upload all outgoing records.  |[mozilla-mobile/android-components#3092](https://github.com/mozilla-mobile/android-components/pull/3092)||never |2 |
| bookmarks_sync.remote_tree_problems |[labeled_counter](https://mozilla.github.io/glean/book/user/metrics/labeled_counters.html) |Records counts for structure problems and divergences in the remote bookmarks tree. These are documented in https://github.com/mozilla/dogear/blob/fbade15f2a4f11215e30b8f428a0a8df3defeaec/src/tree.rs#L1273-L1294.  |[mozilla-mobile/android-components#3092](https://github.com/mozilla-mobile/android-components/pull/3092)|<ul><li>orphans</li><li>misparented_roots</li><li>multiple_parents_by_children</li><li>missing_parent_guids</li><li>non_folder_parent_guids</li><li>parent_child_disagreements</li><li>missing_children</li></ul>|never |2 |
| bookmarks_sync.started_at |[datetime](https://mozilla.github.io/glean/book/user/metrics/datetime.html) |Records when the bookmark sync started.  |[mozilla-mobile/android-components#3092](https://github.com/mozilla-mobile/android-components/pull/3092)||never |2 |
| bookmarks_sync.uid |[string](https://mozilla.github.io/glean/book/user/metrics/string.html) |The user's hashed Firefox Account ID.  |[mozilla-mobile/android-components#3092](https://github.com/mozilla-mobile/android-components/pull/3092)||never |2 |
| sync.sync_uuid |[uuid](https://mozilla.github.io/glean/book/user/metrics/uuid.html) |Unique identifier for this sync, used to correlate together individual pings for data types that were synchronized together (history, bookmarks, logins). If a data type is synchronized by itself via the legacy 'sync' API (as opposed to the Sync Manager), then this field will not be set on the corresponding ping.  |[mozilla-mobile/android-components#5386](https://github.com/mozilla-mobile/android-components/pull/5386#pullrequestreview-392363687)||never |1 |

## creditcards-sync

A ping sent for every Credit Cards engine sync. It doesn't include the `client_id` because it reports a hashed version of the user's Firefox Account ID.


**Data reviews for this ping:**

- <https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481>

**Bugs related to this ping:**

- <https://github.com/mozilla-mobile/android-components/issues/10371>

All Glean pings contain built-in metrics in the [`ping_info`](https://mozilla.github.io/glean/book/user/pings/index.html#the-ping_info-section) and [`client_info`](https://mozilla.github.io/glean/book/user/pings/index.html#the-client_info-section) sections.

In addition to those built-in metrics, the following metrics are added to the ping:

| Name | Type | Description | Data reviews | Extras | Expiration | [Data Sensitivity](https://wiki.mozilla.org/Firefox/Data_Collection) |
| --- | --- | --- | --- | --- | --- | --- |
| creditcards_sync.failure_reason |[labeled_string](https://mozilla.github.io/glean/book/user/metrics/labeled_strings.html) |Records why the credit cards sync failed: either due to an authentication error, unexpected exception, or other error. The error strings are truncated and sanitized to omit PII, like URLs and file system paths.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)|<ul><li>other</li><li>unexpected</li><li>auth</li></ul>|never |2 |
| creditcards_sync.finished_at |[datetime](https://mozilla.github.io/glean/book/user/metrics/datetime.html) |Records when the credit cards sync finished. This includes the time to download, apply, and upload all records.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)||never |2 |
| creditcards_sync.incoming |[labeled_counter](https://mozilla.github.io/glean/book/user/metrics/labeled_counters.html) |Records incoming credit cards record counts. `applied` is the number of incoming records that were successfully stored or updated in the local database. `failed_to_apply` is the number of records that were ignored due to errors. `reconciled` is the number of merged records.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)|<ul><li>applied</li><li>failed_to_apply</li><li>reconciled</li></ul>|never |2 |
| creditcards_sync.outgoing |[labeled_counter](https://mozilla.github.io/glean/book/user/metrics/labeled_counters.html) |Records outgoing credit cards record counts. `uploaded` is the number of records that were successfully sent to the server. `failed_to_upload` is the number of records that weren't uploaded, and will be retried on the next sync.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)|<ul><li>uploaded</li><li>failed_to_upload</li></ul>|never |2 |
| creditcards_sync.outgoing_batches |[counter](https://mozilla.github.io/glean/book/user/metrics/counter.html) |Records the number of batches needed to upload all outgoing records. The Sync server has a hard limit on the number of records (and request body bytes) on the number of records that can fit into a single batch, and large syncs may require multiple batches.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)||never |2 |
| creditcards_sync.started_at |[datetime](https://mozilla.github.io/glean/book/user/metrics/datetime.html) |Records when the credit cards sync started.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)||never |2 |
| creditcards_sync.uid |[string](https://mozilla.github.io/glean/book/user/metrics/string.html) |The user's hashed Firefox Account ID.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)||never |2 |

## history-sync

A ping sent for every history sync. It doesn't include the `client_id` because it reports a hashed version of the user's Firefox Account ID.


**Data reviews for this ping:**

- <https://github.com/mozilla-mobile/android-components/pull/3092>

**Bugs related to this ping:**

- <https://github.com/mozilla-mobile/android-components/pull/3092>

All Glean pings contain built-in metrics in the [`ping_info`](https://mozilla.github.io/glean/book/user/pings/index.html#the-ping_info-section) and [`client_info`](https://mozilla.github.io/glean/book/user/pings/index.html#the-client_info-section) sections.

In addition to those built-in metrics, the following metrics are added to the ping:

| Name | Type | Description | Data reviews | Extras | Expiration | [Data Sensitivity](https://wiki.mozilla.org/Firefox/Data_Collection) |
| --- | --- | --- | --- | --- | --- | --- |
| history_sync.failure_reason |[labeled_string](https://mozilla.github.io/glean/book/user/metrics/labeled_strings.html) |Records why the history sync failed: either due to an authentication error, unexpected exception, or other error. The error strings are truncated and sanitized to omit PII, like URLs and file system paths.  |[mozilla-mobile/android-components#3092](https://github.com/mozilla-mobile/android-components/pull/3092)|<ul><li>other</li><li>unexpected</li><li>auth</li></ul>|never |2 |
| history_sync.finished_at |[datetime](https://mozilla.github.io/glean/book/user/metrics/datetime.html) |Records when the history sync finished. This includes the time to download, apply, and upload all records.  |[mozilla-mobile/android-components#3092](https://github.com/mozilla-mobile/android-components/pull/3092)||never |2 |
| history_sync.incoming |[labeled_counter](https://mozilla.github.io/glean/book/user/metrics/labeled_counters.html) |Records incoming history record counts. `applied` is the number of incoming history pages that were successfully stored or updated in the local database. `failed_to_apply` is the number of pages that were ignored due to errors. `reconciled` is the number of pages with new visits locally and remotely, and had their visits merged.  |[mozilla-mobile/android-components#3092](https://github.com/mozilla-mobile/android-components/pull/3092)|<ul><li>applied</li><li>failed_to_apply</li><li>reconciled</li></ul>|never |2 |
| history_sync.outgoing |[labeled_counter](https://mozilla.github.io/glean/book/user/metrics/labeled_counters.html) |Records outgoing history record counts. `uploaded` is the number of records that were successfully sent to the server. `failed_to_upload` is the number of records that weren't uploaded, and will be retried on the next sync.  |[mozilla-mobile/android-components#3092](https://github.com/mozilla-mobile/android-components/pull/3092)|<ul><li>uploaded</li><li>failed_to_upload</li></ul>|never |2 |
| history_sync.outgoing_batches |[counter](https://mozilla.github.io/glean/book/user/metrics/counter.html) |Records the number of batches needed to upload all outgoing records. The Sync server has a hard limit on the number of records (and request body bytes) on the number of records that can fit into a single batch, and large syncs may require multiple batches.  |[mozilla-mobile/android-components#3092](https://github.com/mozilla-mobile/android-components/pull/3092)||never |2 |
| history_sync.started_at |[datetime](https://mozilla.github.io/glean/book/user/metrics/datetime.html) |Records when the history sync started.  |[mozilla-mobile/android-components#3092](https://github.com/mozilla-mobile/android-components/pull/3092)||never |2 |
| history_sync.uid |[string](https://mozilla.github.io/glean/book/user/metrics/string.html) |The user's hashed Firefox Account ID.  |[mozilla-mobile/android-components#3092](https://github.com/mozilla-mobile/android-components/pull/3092)||never |2 |
| sync.sync_uuid |[uuid](https://mozilla.github.io/glean/book/user/metrics/uuid.html) |Unique identifier for this sync, used to correlate together individual pings for data types that were synchronized together (history, bookmarks, logins). If a data type is synchronized by itself via the legacy 'sync' API (as opposed to the Sync Manager), then this field will not be set on the corresponding ping.  |[mozilla-mobile/android-components#5386](https://github.com/mozilla-mobile/android-components/pull/5386#pullrequestreview-392363687)||never |1 |

## logins-sync

A ping sent for every logins/passwords sync. It doesn't include the `client_id` because it reports a hashed version of the user's Firefox Account ID.


**Data reviews for this ping:**

- <https://github.com/mozilla-mobile/android-components/pull/5294>

**Bugs related to this ping:**

- <https://github.com/mozilla-mobile/android-components/issues/4556>

All Glean pings contain built-in metrics in the [`ping_info`](https://mozilla.github.io/glean/book/user/pings/index.html#the-ping_info-section) and [`client_info`](https://mozilla.github.io/glean/book/user/pings/index.html#the-client_info-section) sections.

In addition to those built-in metrics, the following metrics are added to the ping:

| Name | Type | Description | Data reviews | Extras | Expiration | [Data Sensitivity](https://wiki.mozilla.org/Firefox/Data_Collection) |
| --- | --- | --- | --- | --- | --- | --- |
| logins_sync.failure_reason |[labeled_string](https://mozilla.github.io/glean/book/user/metrics/labeled_strings.html) |Records why the passwords sync failed: either due to an authentication error, unexpected exception, or other error. The error strings are truncated and sanitized to omit PII, like usernames and passwords.  |[mozilla-mobile/android-components#5294](https://github.com/mozilla-mobile/android-components/pull/5294)|<ul><li>other</li><li>unexpected</li><li>auth</li></ul>|never |2 |
| logins_sync.finished_at |[datetime](https://mozilla.github.io/glean/book/user/metrics/datetime.html) |Records when the passwords sync finished. This includes the time to download, apply, and upload all records.  |[mozilla-mobile/android-components#5294](https://github.com/mozilla-mobile/android-components/pull/5294)||never |2 |
| logins_sync.incoming |[labeled_counter](https://mozilla.github.io/glean/book/user/metrics/labeled_counters.html) |Records incoming passwords record counts. `applied` is the number of incoming passwords entries that were successfully stored or updated in the local database. `failed_to_apply` is the number of entries that were ignored due to errors. `reconciled` is the number of entries with changes both locally and remotely that were merged.  |[mozilla-mobile/android-components#5294](https://github.com/mozilla-mobile/android-components/pull/5294)|<ul><li>applied</li><li>failed_to_apply</li><li>reconciled</li></ul>|never |2 |
| logins_sync.outgoing |[labeled_counter](https://mozilla.github.io/glean/book/user/metrics/labeled_counters.html) |Records outgoing passwords record counts. `uploaded` is the number of records that were successfully sent to the server. `failed_to_upload` is the number of records that weren't uploaded, and will be retried on the next sync.  |[mozilla-mobile/android-components#5294](https://github.com/mozilla-mobile/android-components/pull/5294)|<ul><li>uploaded</li><li>failed_to_upload</li></ul>|never |2 |
| logins_sync.outgoing_batches |[counter](https://mozilla.github.io/glean/book/user/metrics/counter.html) |Records the number of batches needed to upload all outgoing records. The Sync server has a hard limit on the number of records (and request body bytes) on the number of records that can fit into a single batch, and large syncs may require multiple batches.  |[mozilla-mobile/android-components#5294](https://github.com/mozilla-mobile/android-components/pull/5294)||never |2 |
| logins_sync.started_at |[datetime](https://mozilla.github.io/glean/book/user/metrics/datetime.html) |Records when the passwords sync started.  |[mozilla-mobile/android-components#5294](https://github.com/mozilla-mobile/android-components/pull/5294)||never |2 |
| logins_sync.uid |[string](https://mozilla.github.io/glean/book/user/metrics/string.html) |The user's hashed Firefox Account ID.  |[mozilla-mobile/android-components#5294](https://github.com/mozilla-mobile/android-components/pull/5294)||never |2 |
| sync.sync_uuid |[uuid](https://mozilla.github.io/glean/book/user/metrics/uuid.html) |Unique identifier for this sync, used to correlate together individual pings for data types that were synchronized together (history, bookmarks, logins). If a data type is synchronized by itself via the legacy 'sync' API (as opposed to the Sync Manager), then this field will not be set on the corresponding ping.  |[mozilla-mobile/android-components#5386](https://github.com/mozilla-mobile/android-components/pull/5386#pullrequestreview-392363687)||never |1 |

## sync

A summary ping, sent every time a sync is performed. During each Sync one or more data types could be synchronized, depending on which data types user configured to sync. Alongside with 'sync' ping one or more individual data type specific pings will be sent. For example, if history and bookmarks data types are configured to be synchronized, the following pings will be sent: 'sync', 'history-sync' and 'bookmarks-sync'. Alternatively, if only history is configured to be synchronized then 'sync' and 'history-sync' pings will be sent. In case of a "global failure" where none of the data type syncs could even start, e.g. device is offline, only the 'sync' ping will be sent. This ping doesn't include the `client_id` because it reports a hashed version of the user's Firefox Account ID.


**Data reviews for this ping:**

- <https://github.com/mozilla-mobile/android-components/pull/5386#pullrequestreview-392363687>

**Bugs related to this ping:**

- <https://github.com/mozilla-mobile/android-components/issues/5371>

All Glean pings contain built-in metrics in the [`ping_info`](https://mozilla.github.io/glean/book/user/pings/index.html#the-ping_info-section) and [`client_info`](https://mozilla.github.io/glean/book/user/pings/index.html#the-client_info-section) sections.

In addition to those built-in metrics, the following metrics are added to the ping:

| Name | Type | Description | Data reviews | Extras | Expiration | [Data Sensitivity](https://wiki.mozilla.org/Firefox/Data_Collection) |
| --- | --- | --- | --- | --- | --- | --- |
| fxa_tab.received |[event](https://mozilla.github.io/glean/book/user/metrics/event.html) |Recorded when a tab is received.  Also sent by desktop - see also the docs at https://firefox-source-docs.mozilla.org/toolkit/components/telemetry/data/sync-ping.html  |[Bug 1652902](https://bugzilla.mozilla.org/show_bug.cgi?id=1652902)|<ul><li>flow_id: A guid, unique for the URL being sent but common for all target devices. </li><li>reason: The reason we discovered the tab. Will be one of 'push', 'push-missed' or 'poll'. </li><li>stream_id: A guid, unique for both the URL being sent and the target device. </li></ul>|never | |
| fxa_tab.sent |[event](https://mozilla.github.io/glean/book/user/metrics/event.html) |Recorded when a tab is sent. Also sent by desktop - see also the docs at https://firefox-source-docs.mozilla.org/toolkit/components/telemetry/data/sync-ping.html  |[Bug 1652902](https://bugzilla.mozilla.org/show_bug.cgi?id=1652902)|<ul><li>flow_id: A guid, unique for the URL being sent but common for all target devices. The value is randomly generated so can not identify details about the user or tab. </li><li>stream_id: A guid, unique for both the URL being sent and the target device. The value is randomly generated so can not identify details about the user or tab. </li></ul>|never | |
| sync.failure_reason |[labeled_string](https://mozilla.github.io/glean/book/user/metrics/labeled_strings.html) |Records a global sync failure: either due to an authentication error, unexpected exception, or other error that caused the sync to fail. Error strings are truncated and sanitized to omit PII, like URLs and file system paths.  |[mozilla-mobile/android-components#3092](https://github.com/mozilla-mobile/android-components/pull/3092)|<ul><li>other</li><li>unexpected</li><li>auth</li></ul>|never |2 |
| sync.sync_uuid |[uuid](https://mozilla.github.io/glean/book/user/metrics/uuid.html) |Unique identifier for this sync, used to correlate together individual pings for data types that were synchronized together (history, bookmarks, logins). If a data type is synchronized by itself via the legacy 'sync' API (as opposed to the Sync Manager), then this field will not be set on the corresponding ping.  |[mozilla-mobile/android-components#5386](https://github.com/mozilla-mobile/android-components/pull/5386#pullrequestreview-392363687)||never |1 |

## tabs-sync

A ping sent for every Tabs engine sync. It doesn't include the `client_id` because it reports a hashed version of the user's Firefox Account ID.


**Data reviews for this ping:**

- <https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481>

**Bugs related to this ping:**

- <https://github.com/mozilla-mobile/android-components/issues/10371>

All Glean pings contain built-in metrics in the [`ping_info`](https://mozilla.github.io/glean/book/user/pings/index.html#the-ping_info-section) and [`client_info`](https://mozilla.github.io/glean/book/user/pings/index.html#the-client_info-section) sections.

In addition to those built-in metrics, the following metrics are added to the ping:

| Name | Type | Description | Data reviews | Extras | Expiration | [Data Sensitivity](https://wiki.mozilla.org/Firefox/Data_Collection) |
| --- | --- | --- | --- | --- | --- | --- |
| tabs_sync.failure_reason |[labeled_string](https://mozilla.github.io/glean/book/user/metrics/labeled_strings.html) |Records why the tabs sync failed: either due to an authentication error, unexpected exception, or other error. The error strings are truncated and sanitized to omit PII, like URLs and file system paths.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)|<ul><li>other</li><li>unexpected</li><li>auth</li></ul>|never |2 |
| tabs_sync.finished_at |[datetime](https://mozilla.github.io/glean/book/user/metrics/datetime.html) |Records when the tabs sync finished. This includes the time to download, apply, and upload all records.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)||never |2 |
| tabs_sync.incoming |[labeled_counter](https://mozilla.github.io/glean/book/user/metrics/labeled_counters.html) |Records incoming tabs record counts. `applied` is the number of incoming records that were successfully stored or updated in the local database. `failed_to_apply` is the number of records that were ignored due to errors. `reconciled` is the number of merged records.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)|<ul><li>applied</li><li>failed_to_apply</li><li>reconciled</li></ul>|never |2 |
| tabs_sync.outgoing |[labeled_counter](https://mozilla.github.io/glean/book/user/metrics/labeled_counters.html) |Records outgoing tabs record counts. `uploaded` is the number of records that were successfully sent to the server. `failed_to_upload` is the number of records that weren't uploaded, and will be retried on the next sync.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)|<ul><li>uploaded</li><li>failed_to_upload</li></ul>|never |2 |
| tabs_sync.outgoing_batches |[counter](https://mozilla.github.io/glean/book/user/metrics/counter.html) |Records the number of batches needed to upload all outgoing records. The Sync server has a hard limit on the number of records (and request body bytes) on the number of records that can fit into a single batch, and large syncs may require multiple batches.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)||never |2 |
| tabs_sync.started_at |[datetime](https://mozilla.github.io/glean/book/user/metrics/datetime.html) |Records when the tabs sync started.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)||never |2 |
| tabs_sync.uid |[string](https://mozilla.github.io/glean/book/user/metrics/string.html) |The user's hashed Firefox Account ID.  |[mozilla-mobile/android-components#10372](https://github.com/mozilla-mobile/android-components/pull/10372#issuecomment-850378481)||never |2 |

Data categories are [defined here](https://wiki.mozilla.org/Firefox/Data_Collection).

<!-- AUTOGENERATED BY glean_parser v6.1.1. DO NOT EDIT. -->

