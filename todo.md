NOTAS:

TODO:

Preguntar:

- Porq cada vez se selecciona una k (selector) distinta???! -> problema de todo el feature selection

""" Study of the parameters of the Gradient Boosting Classifier """

np.random.seed(2)

balanced, balanced2, balanced3, balanced4, balanced5 = [], [], [], [], []
features, features2, features3, features4, features5, features6 = [], [], [], [], [], []

a_n_estimators = [50, 100, 150, 300, 600]  # Number of boosting stages - The more the better score (ad infinitum) but the longer the training
a_learning_rate = [0.01, 0.1, 1.0, 2.0, 3.0]
a_max_depth = [2, 5, 10, 15, 20]
a_subsample = [0.1, 0.2, 0.3, 0.5, 0.8, 1.0] # < 1.0 leads to a reduction of variance and an increase of bias
a_min_samples_split = [2, 5, 10, 20]
a_selector_k = [10, 20, 25, 30, 40, 45, 46, 47, "all"]

for i in a_selector_k:
    folds_array = []
    # model_gb = GridSearchCV(
    #     preprocessing_pipeline_gb,
    #     {"selector__k": [10]},
    #     cv=stratified_kfold_last_split(folds_array),
    #     scoring="balanced_accuracy",
    #     n_jobs=-1,
    # )
    # model_gb.fit(X_train, y_train)
    model_gb_feature = GridSearchCV(
        preprocessing_pipeline_feature_gb,
        {"selector__k": [i]},
        cv=stratified_kfold_last_split(folds_array),
        scoring="balanced_accuracy",
        n_jobs=-1,
    )
    model_gb_feature.fit(X_train, y_train)
    # balanced6.append(model_gb.best_score_)
    features6.append(model_gb_feature.best_score_)

# Plot ax6

fig6, ax6 = plt.subplots()

# ax6.plot(a_selector_k, balanced6, label="Balanced accuracy")

ax6.plot(a_selector_k, features6, label="Balanced accuracy with selector k")
ax6.set_xlabel("selector_k")
ax6.set_ylabel("Balanced accuracy")
ax6.legend()

plt.tight_layout()
plt.rcParams['figure.figsize'] = [10, 2]
plt.show()
