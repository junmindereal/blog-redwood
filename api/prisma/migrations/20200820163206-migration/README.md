# Migration `20200820163206-migration`

This migration has been generated by Junmin De Real at 8/20/2020, 4:32:06 PM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
CREATE TABLE "public"."Post" (
"id" SERIAL,
"title" text  NOT NULL ,
"body" text  NOT NULL ,
"createdAt" timestamp(3)  NOT NULL DEFAULT CURRENT_TIMESTAMP,
PRIMARY KEY ("id"))
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration ..20200820163206-migration
--- datamodel.dml
+++ datamodel.dml
@@ -1,0 +1,16 @@
+datasource DS {
+  provider = "postgresql"
+  url = "***"
+}
+
+generator client {
+  provider      = "prisma-client-js"
+  binaryTargets = "native"
+}
+
+model Post {
+  id Int @id @default(autoincrement())
+  title String
+  body String
+  createdAt DateTime @default(now())
+}
```


