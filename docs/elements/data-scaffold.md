# Data Scaffold

`DataScaffold` is a widget that handles a `AsyncValue` from a provides a scaffold with a loading, error and data state.

## Usage

The following code is an example of how to use `DataScaffold` in combination with `dashboardProvider`.




```js
@Riverpod(keepAlive: true)
class Dashboard extends _$Dashboard {
  @override
  FutureOr<String> build() {
    return 'Dashboard';
  }
}
```

```js
@RoutePage()
class DashboardScreen extends ConsumerWidget {
  const DashboardScreen({super.key});

  @override
  Widget build(BuildContext context, WidgetRef ref) {
    return DataScaffold(
        value: ref.watch(dashboardProvider),
        onData: (data) {
          return Center(
            child: Text(data),
          );
        });
  }
}

```